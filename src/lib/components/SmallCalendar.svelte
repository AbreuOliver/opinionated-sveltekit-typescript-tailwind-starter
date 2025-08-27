<script lang="ts">
	import { onMount } from 'svelte';

	interface Event {
		date: string;
		formattedDate: string;
		title: string;
		description: string;
	}

	interface EventMap {
		[key: string]: Event[];
	}

	let currentDate: Date = new Date();
	let currentMonth: number = currentDate.getMonth();
	let currentYear: number = currentDate.getFullYear();
	let currentMonthTitle: string = '';
	let nextMonthTitle: string = '';
	let currentMonthDays: (number | string)[] = [];
	let nextMonthDays: (number | string)[] = [];
	let currentMonthEvents: Event[] = [];
	let nextMonthEvents: Event[] = [];

	const events = {
		'2024-12': [
			{
				date: '12/15/2024',
				formattedDate: 'Sun, Dec 15',
				title: 'Christmas Cantata',
				description: ''
			},
			{
				date: '12/22/2024',
				formattedDate: 'Sun, Dec 22',
				title: "Lord's Supper",
				description: ''
			},
			{
				date: '12/30/2024 - 01/01/2025',
				formattedDate: 'Mon, Dec 30 - Wed, Jan 01',
				title: 'Mid Atlantic Youth Conference',
				description: ''
			}
		],
		'2025-01': [
			{
				date: '01/05/2025',
				formattedDate: 'Sun, Jan 05',
				title: 'Vision Sunday',
				description: ''
			},
			{
				date: '01/30/2025',
				formattedDate: 'Thu, Jan 30',
				title: 'Marriage Retreat',
				description: ''
			},
			{
				date: '01/31/2025',
				formattedDate: 'Fri, Jan 31',
				title: 'Marriage Retreat',
				description: ''
			}
		],
		'2025-03': [
			{
				date: '03/07/2025 - 03/09/2025',
				formattedDate: 'Fri, Mar 07 - Sun, Mar 09',
				title: 'Revival with Scott Pauley',
				description:
					'Fri, Mar 7 at 7:00 PM,\n Sat, Mar 8 at 5:00 PM,\n Sun, Mar 9 at 11:00 AM & 6:00 PM'
			},
			{
				date: '03/11/2025',
				formattedDate: 'Tue, Mar 11',
				title: '40 Days of Prayer & Fasting',
				description: ''
			},
			{
				date: '03/30/2025',
				formattedDate: 'Sun, Mar 30',
				title: "Lord's Supper",
				description: ''
			}
		],
		'2025-04': [
			{
				date: '04/03/2025',
				formattedDate: 'Thu, Apr 03',
				title: 'Easter Outreach',
				description: ''
			},
			{
				date: '04/10/2025',
				formattedDate: 'Thu, Apr 10',
				title: 'Easter Outreach',
				description: ''
			},
			{
				date: '04/17/2025',
				formattedDate: 'Thu, Apr 17',
				title: 'Easter Outreach',
				description: ''
			},
			{
				date: '04/19/2025',
				formattedDate: 'Sat, Apr 19',
				title: 'Super Saturday Saturation',
				description: ''
			},
			{
				date: '04/20/2025',
				formattedDate: 'Sun, Apr 20',
				title: 'Easter Sunday',
				description: ''
			}
		],
		'2025-05': [
			{
				date: '05/11/2025',
				formattedDate: 'Sun, May 11',
				title: "Mother's Day",
				description: ''
			},
			{
				date: '05/18/2025',
				formattedDate: 'Sun, May 18',
				title: 'Graduation Celebration',
				description: ''
			}
		],
		'2025-06': [
			{
				date: '06/01/2025',
				formattedDate: 'Sun, Jun 01',
				title: "Lord's Supper",
				description: ''
			},
			{
				date: '06/15/2025',
				formattedDate: 'Sun, Jun 15',
				title: "Father's Day",
				description: ''
			},
			{
				date: '06/22/2025 - 06/25/2025',
				formattedDate: 'Sun, Jun 22 - Wed, Jun 25',
				title: 'Vacation Bible School (VBS)',
				description: ''
			}
		],
		'2025-07': [
			{
				date: '06/01/2025',
				formattedDate: 'Sun, Jun 01',
				title: "Lord's Supper",
				description: ''
			},
			{
				date: '06/15/2025',
				formattedDate: 'Sun, Jun 15',
				title: "Father's Day",
				description: ''
			},
			{
				date: '06/22/2025 - 06/25/2025',
				formattedDate: 'Sun, Jun 22 - Wed, Jun 25',
				title: 'Vacation Bible School (VBS)',
				description: ''
			}
		],
		'2025-08': [
			{
				date: '08/02/2025',
				formattedDate: 'Sat, Aug 02',
				title: 'Teacher Appreciation Meal',
				description: ''
			},
			{
				date: '08/03/2025',
				formattedDate: 'Sun, Aug 03',
				title: "'Move-Up' Sunday",
				description: ''
			},
			{
				date: '08/24/2025 - 08/29/2025',
				formattedDate: 'Sun, Aug 24 - Fri, Aug 29',
				title: 'Revival Services with Dr. Benny Beckum',
				description: ''
			}
		],
		'2025-09': [
			{
				date: '09/07/2025',
				formattedDate: 'Sun, Sep 07',
				title: "Grandparent's Day",
				description: ''
			},
			{
				date: '09/07/2025',
				formattedDate: 'Sun, Sep 07',
				title: "Lord's Supper",
				description: ''
			}
		],
		'2025-10': [
			{
				date: '10/17/2025',
				formattedDate: 'Fri, Oct 17',
				title: 'AGM',
				description: ''
			},
			{
				date: '10/25/2025',
				formattedDate: 'Sat, Oct 25',
				title: 'Big Bus Day',
				description: ''
			},
			{
				date: '10/26/2025',
				formattedDate: 'Sun, Cct 26',
				title: 'Anniversary Sunday with Brady Rochester Family',
				description: ''
			}
		],
		'2025-11': [
			{
				date: '11/22/2025',
				formattedDate: 'Sat, Nov 22',
				title: 'Fall Festival',
				description: ''
			}
		],
		'2025-12': [
			{
				date: '12/14/2025',
				formattedDate: 'Sun, Dec 14',
				title: 'Christmas Cantata',
				description: ''
			},
			{
				date: '12/21/2025',
				formattedDate: 'Sun, Dec 21',
				title: "Lord's Supper",
				description: ''
			}
		]
	};

	function renderCalendar(year: number, month: number): (number | string)[] {
		const firstDay: number = new Date(year, month, 1).getDay();
		const daysInMonth: number = new Date(year, month + 1, 0).getDate();
		const adjustedFirstDay: number = firstDay;

		return Array.from({ length: 42 }, (_, i: number) => {
			const day = i - adjustedFirstDay + 1;
			return day > 0 && day <= daysInMonth ? day : '';
		});
	}

	function getNextMonthWithEvents(year: number, month: number): { year: number; month: number } {
		let currentYear = year;
		let currentMonth = month;

		// Look ahead up to 12 months to avoid infinite loop
		for (let i = 0; i < 12; i++) {
			currentMonth++;
			if (currentMonth > 11) {
				currentMonth = 0;
				currentYear++;
			}

			const eventsKey = `${currentYear}-${String(currentMonth + 1).padStart(2, '0')}`;
			if (events[eventsKey]?.length > 0) {
				return { year: currentYear, month: currentMonth };
			}
		}

		// If no months with events found, return the next month
		return { year, month: month + 1 };
	}

	function isCurrentDate(day: number, year: number, month: number): boolean {
		const today = new Date();
		return day === today.getDate() && month === today.getMonth() && year === today.getFullYear();
	}

	function getMonthEvents(year: number, month: number): Event[] {
		const eventsKey: string = `${year}-${String(month + 1).padStart(2, '0')}`;
		return events[eventsKey] || [];
	}

	function updateCalendar() {
		// First check if current month has events
		const currentMonthKey = `${currentYear}-${String(currentMonth + 1).padStart(2, '0')}`;
		const hasCurrentMonthEvents = events[currentMonthKey]?.length > 0;

		if (!hasCurrentMonthEvents) {
			// Find the next month with events
			const nextMonthWithEvents = getNextMonthWithEvents(currentYear, currentMonth);
			currentYear = nextMonthWithEvents.year;
			currentMonth = nextMonthWithEvents.month;
		}

		// Update current month display
		currentMonthDays = renderCalendar(currentYear, currentMonth);
		currentMonthTitle = `${new Date(currentYear, currentMonth).toLocaleString('default', { month: 'long' })} ${currentYear}`;
		currentMonthEvents = getMonthEvents(currentYear, currentMonth);

		// Find next month with events for second calendar
		const nextMonthData = getNextMonthWithEvents(currentYear, currentMonth);
		const nextDate = new Date(nextMonthData.year, nextMonthData.month, 1);

		nextMonthDays = renderCalendar(nextDate.getFullYear(), nextDate.getMonth());
		nextMonthTitle = `${nextDate.toLocaleString('default', { month: 'long' })} ${nextDate.getFullYear()}`;
		nextMonthEvents = getMonthEvents(nextDate.getFullYear(), nextDate.getMonth());
	}

	const formattedDate = (date: string): string => {
		const eventDate: Date = new Date(date);
		return new Intl.DateTimeFormat('en-US', {
			weekday: 'short',
			month: 'short',
			day: 'numeric'
		}).format(eventDate);
	};

	const formattedTime = (time: string): string => {
		const [hours, minutes]: number[] = time.split(':').map(Number);
		const isPM: boolean = hours >= 12;
		const adjustedHours: number = hours % 12 || 12;
		const period: string = isPM ? 'PM' : 'AM';
		return `${adjustedHours}:${String(minutes).padStart(2, '0')} ${period}`;
	};

	onMount(() => {
		updateCalendar();
	});
</script>

<div class="flex flex-wrap gap-6 justify-center p-4">
	<!-- Current Month -->
	<div class="w-full rounded-lg border-2 border-neutral-200 md:w-2/3 lg:w-1/3">
		<div class="p-4 text-xl font-bold text-center bg-transparent border-b border-neutral-300">
			{currentMonthTitle}
		</div>
		<div class="grid grid-cols-7 gap-1 p-4">
			<div class="font-semibold text-center">Su</div>
			<div class="font-semibold text-center">Mo</div>
			<div class="font-semibold text-center">Tu</div>
			<div class="font-semibold text-center">We</div>
			<div class="font-semibold text-center">Th</div>
			<div class="font-semibold text-center">Fr</div>
			<div class="font-semibold text-center">Sa</div>

			{#each currentMonthDays as day}
				<div
					class="h-10 flex flex-col items-center justify-center text-sm border border-neutral-200/50 hover:border-neutral-300 rounded-md relative
				{day ? 'bg-white' : 'bg-neutral-50 text-neutral-300'}"
				>
					{#if isCurrentDate(day, currentYear, currentMonth)}
						<div class="absolute top-0 w-full h-full bg-theme-900/20 rounded-md"></div>
					{/if}
					{day}
				</div>
			{/each}
		</div>
		<div class="p-8 mt-2 w-full bg-neutral-100 border-t border-neutral-200">
			<!-- <h3 class="text-lg font-semibold">Events</h3> -->
			{#each currentMonthEvents as event}
				<div class="pb-4 mb-4 border-b border-neutral-400 border-dashed">
					<p class="text-lg font-bold">{event.formattedDate}</p>
					<p class="text-lg font-medium">
						{event.title}
					</p>
					{#if event.description}
						<!-- <p class="text-base text-neutral-400">{event.description}</p> -->
						<p class="text-base text-neutral-500 whitespace-pre-line pl-2 pt-1">
							{event.description}
						</p>
					{/if}
				</div>
			{/each}
		</div>
	</div>

	<!-- Next Month -->
	<div class="w-full rounded-lg border-2 border-neutral-200 md:w-2/4 lg:w-1/3">
		<div class="p-4 text-xl font-bold text-center bg-transparent border-b border-neutral-300">
			{nextMonthTitle}
		</div>
		<div class="grid grid-cols-7 gap-1 p-4">
			<div class="font-semibold text-center">Su</div>
			<div class="font-semibold text-center">Mo</div>
			<div class="font-semibold text-center">Tu</div>
			<div class="font-semibold text-center">We</div>
			<div class="font-semibold text-center">Th</div>
			<div class="font-semibold text-center">Fr</div>
			<div class="font-semibold text-center">Sa</div>

			{#each nextMonthDays as day}
				<div
					class="h-10 flex items-center justify-center text-sm border border-neutral-200/50 hover:border-neutral-300 rounded-md
                    {day ? 'bg-white' : 'bg-neutral-50 text-neutral-300'}"
				>
					{day}
				</div>
			{/each}
		</div>
		<div class="p-8 mt-2 w-full bg-neutral-100 border-t border-neutral-200">
			<!-- <h3 class="text-lg font-semibold">Events</h3> -->
			{#each nextMonthEvents as event}
				<div class="pb-4 mb-4 border-b border-neutral-400 border-dashed">
					<p class="text-lg font-bold">{event.formattedDate}</p>
					<p class="text-lg font-medium">
						{event.title}
					</p>
					{#if event.description}
						<!-- <p class="text-base text-neutral-400">{event.description}</p> -->
						<p class="text-base text-neutral-500 whitespace-pre-line pl-2 pt-1">
							{event.description}
						</p>
					{/if}
				</div>
			{/each}
		</div>
	</div>
</div>
