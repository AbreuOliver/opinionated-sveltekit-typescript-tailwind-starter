<script lang="ts">
	import { writable, get } from 'svelte/store';
	import { Button, Modal } from 'flowbite-svelte';
	let defaultModal = false;

	// Constants
	const MONTH_NAMES: string[] = [
		'January',
		'February',
		'March',
		'April',
		'May',
		'June',
		'July',
		'August',
		'September',
		'October',
		'November',
		'December'
	];
	const DAYS: string[] = ['Sun', 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat'];

	// Types
	interface Event {
		date: Date;
		title: string;
	}

	// State
	const today: Date = new Date();
	const month = writable<number>(today.getMonth());
	const year = writable<number>(today.getFullYear());
	const events = writable<Event[]>([
		{
			date: new Date('2024-12-15'),
			title: 'Christmas Cantata'
		},
		{
			date: new Date('2024-12-22'),
			title: "Lord's Supper"
		},
		{
			date: new Date('2024-12-30'),
			title: 'MAYC'
		},
		{
			date: new Date('2024-12-31'),
			title: 'MAYC'
		},
		{
			date: new Date('2025-01-05'),
			title: 'Vision Sunday'
		},
		{
			date: new Date('2025-01-30'),
			title: 'Marrriage Retreat'
		},
		{
			date: new Date('2025-01-31'),
			title: 'Marrriage Retreat'
		}
	]);

	// Calendar variables for both months
	let blankDays1: number[] = [];
	let daysInMonth1: number[] = [];
	let blankDays2: number[] = [];
	let daysInMonth2: number[] = [];

	// Helper function to normalize a date by stripping the time component
	function normalizeDate(date: Date): string {
		return new Date(date.getFullYear(), date.getMonth(), date.getDate()).toDateString();
	}

	// Calendar Logic
	function updateCalendars(): void {
		const currentMonth1 = get(month);
		const currentYear1 = get(year);
		const currentMonth2 = (currentMonth1 + 1) % 12;
		const currentYear2 = currentMonth1 === 11 ? currentYear1 + 1 : currentYear1;

		// First month
		const firstDay1 = new Date(currentYear1, currentMonth1, 1).getDay();
		const totalDays1 = new Date(currentYear1, currentMonth1 + 1, 0).getDate();
		blankDays1 = Array.from({ length: firstDay1 });
		daysInMonth1 = Array.from({ length: totalDays1 }, (_, i) => i + 1);

		// Second month
		const firstDay2 = new Date(currentYear2, currentMonth2, 1).getDay();
		const totalDays2 = new Date(currentYear2, currentMonth2 + 1, 0).getDate();
		blankDays2 = Array.from({ length: firstDay2 });
		daysInMonth2 = Array.from({ length: totalDays2 }, (_, i) => i + 1);
	}

	$: updateCalendars();

	function getEventsForDate(day: number, monthOffset: number): Event[] {
		const targetDate = normalizeDate(new Date(get(year), get(month) + monthOffset, day));
		return get(events).filter((event) => normalizeDate(event.date) === targetDate);
	}

	function isToday(day: number, monthOffset: number): boolean {
		const currentDate = normalizeDate(new Date(get(year), get(month) + monthOffset, day));
		return currentDate === normalizeDate(today);
	}

	let selectedEvents: Event[] = [];
	const showModal = writable<boolean>(false);

	function openModal(day: number, monthOffset: number): void {
		selectedEvents = getEventsForDate(day, monthOffset);
		if (selectedEvents.length > 0) {
			showModal.set(true);
		}
	}
</script>

<div class="items-center mx-6 space-y-8 max-w-5xl bg-white rounded-lg border shadow md:mx-auto">
	<!-- First Month -->
	<div>
		<div class="flex justify-between px-6 py-4">
			<h2 class="text-xl">
				<span class="font-bold">{MONTH_NAMES[get(month)]}</span>
				{get(year)}
			</h2>
		</div>
		<div class="grid grid-cols-7 border-t">
			{#each DAYS as day}
				<div class="py-2 text-xs font-bold text-center uppercase">{day}</div>
			{/each}
			{#each blankDays1 as _}
				<div class="h-24"></div>
			{/each}
			{#each daysInMonth1 as day}
				<div
					class="relative h-24"
					on:click={() => (defaultModal = true)}
					on:keydown={(event) => {
						if (event.key === 'Enter' || event.key === ' ') {
							event.preventDefault();
							openModal(day - 1, 0);
						}
					}}
					role="button"
					tabindex="0"
				>
					<div
						class="flex justify-center items-center mx-auto w-8 h-8 rounded-full"
						class:bg-theme-800={isToday(day, 0)}
						class:text-white={isToday(day, 0)}
					>
						{day}
					</div>
					{#each getEventsForDate(day - 1, 0) as event}
						<div class="p-1 mt-2 text-xs text-center text-white rounded bg-theme-900">
							{event.title}
						</div>
					{/each}
				</div>
			{/each}
		</div>
	</div>

	<!-- Second Month -->
	<div>
		<div class="flex justify-between px-6 py-4 border-t">
			<h2 class="text-xl">
				<span class="font-bold">{MONTH_NAMES[(get(month) + 1) % 12]}</span>
				{get(month) === 11 ? get(year) + 1 : get(year)}
			</h2>
		</div>
		<div class="grid grid-cols-7 border-t">
			{#each DAYS as day}
				<div class="py-2 text-xs font-bold text-center uppercase">{day}</div>
			{/each}
			{#each blankDays2 as _}
				<div class="h-24"></div>
			{/each}
			{#each daysInMonth2 as day}
				<div
					class="relative h-24"
					on:click={() => (defaultModal = true)}
					on:keydown={(event) => {
						if (event.key === 'Enter' || event.key === ' ') {
							event.preventDefault();
							defaultModal = true;
							openModal(day - 1, 1);
						}
					}}
					role="button"
					tabindex="0"
				>
					<div
						class="flex justify-center items-center mx-auto w-8 h-8 rounded-full"
						class:bg-theme-800={isToday(day, 1)}
						class:text-white={isToday(day, 1)}
					>
						{day}
					</div>
					{#each getEventsForDate(day - 1, 1) as event}
						<div class="p-1 mt-2 text-xs text-center text-white rounded bg-theme-900">
							{event.title}
						</div>
					{/each}
				</div>
			{/each}
		</div>
	</div>
</div>

<Modal
	title="Event Details"
	bind:open={defaultModal}
	class="mx-auto w-screen rounded-2xl md:w-1/2"
	backdropClass="fixed inset-0 z-40 bg-neutral-900 bg-opacity-50 dark:bg-opacity-80"
	center
	autoclose
>
	<div slot="header" class="text-xl font-bold">Event Details</div>
	<div class="p-4">
		{#if selectedEvents.length > 0}
			{#each selectedEvents as event}
				<div class="mb-4">
					<h3 class="text-lg font-semibold">{event.title}</h3>
					<!-- <p>{event.description}</p> -->
					<p class="text-sm text-neutral-500">{event.date.toLocaleDateString()}</p>
				</div>
			{/each}
		{:else}
			<p>No events for this day.</p>
		{/if}
	</div>
	<div slot="footer" class="flex justify-end">
		<!-- <button
			class="px-4 py-2 text-white rounded bg-theme-600"
		>
			Add to Google Calendar
		</button> -->
	</div>
</Modal>
