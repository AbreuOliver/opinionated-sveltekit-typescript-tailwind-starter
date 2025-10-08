<script lang="ts">
  // Simple types for clarity
  type Link = { label: string; href: string };
  type Paragraph = string | { text: string; link?: Link };
  type Section = { title?: string; paragraphs: Paragraph[] };
  type LegalDoc = { heading: string; updated?: string; sections: Section[] };

  // --- CONTENT (JSON-style data) -------------------------------------------
  const legal: { terms: LegalDoc; privacy: LegalDoc } = {
    terms: {
      heading: 'Terms of Service',
      updated: '2024-11-07',
      sections: [
        {
          title: '1. Introduction',
          paragraphs: [
            `Welcome to the website of Emmanuel Baptist Church (“we”, “our”, or “us”). By accessing
            or using this website (“Site”), you agree to comply with and be bound by these Terms of
            Use. If you do not agree to these terms, please refrain from using the Site.`
          ]
        },
        {
          title: '2. Site Usage',
          paragraphs: [
            `You are permitted to use this Site for lawful purposes only. You may browse the content,
            read articles, watch videos, and engage with any publicly available materials provided.
            Unauthorized use of any content, including but not limited to copying, distribution, or
            modification, is strictly prohibited.`
          ]
        },
        {
          title: '3. No Account Creation',
          paragraphs: [
            `The Site does not require the creation of any user accounts or the submission of personal
            information for access to its content. Users may browse the Site without providing any
            personal data, and we do not store or process any personal data submitted by users.`
          ]
        },
        {
          title: '4. Data Collection and Privacy',
          paragraphs: [
            `While we do not collect any personal data from you directly, we may use third-party
            analytics tools (such as Google Analytics) to gather non-identifiable data about your visit
            to the Site. This data may include information such as your IP address, browser type,
            device, location, and the pages you visit. These analytics are used solely for improving the
            user experience and understanding site traffic patterns. For more information on how we
            handle your data, please refer to our Privacy Policy.`
          ]
        },
        {
          title: '5. Intellectual Property',
          paragraphs: [
            `All content, including text, images, videos, logos, and other materials on the Site, is the
            property of Emmanuel Baptist Church or its content providers and is protected by copyright
            laws. You may not reproduce, distribute, or modify any content from this Site without prior
            written consent from us.`
          ]
        },
        {
          title: '6. Disclaimers',
          paragraphs: [
            `The content provided on this Site is for informational purposes only. While we strive to
            provide accurate and up-to-date information, we make no representations or warranties
            regarding the accuracy, completeness, or reliability of the content. We are not liable for
            any errors or omissions in the information provided on the Site.`,
            `The Site may contain links to third-party websites. We do not control, endorse, or assume
            responsibility for the content, privacy practices, or policies of these external sites.`
          ]
        },
        {
          title: '7. Limitation of Liability',
          paragraphs: [
            `To the fullest extent permitted by law, Emmanuel Baptist Church shall not be liable for any
            direct, indirect, incidental, special, or consequential damages arising out of or related to
            your use of the Site. This includes, but is not limited to, damages for loss of data or
            profits, or due to any errors or omissions in the content.`
          ]
        },
        {
          title: '8. Modifications to Terms',
          paragraphs: [
            `We reserve the right to modify, update, or change these Terms of Use at any time without
            prior notice. Any changes will be posted on this page, and your continued use of the Site
            after such changes constitutes your acceptance of the modified terms.`
          ]
        },
        {
          title: '9. Governing Law',
          paragraphs: [
            `These Terms of Use are governed by the laws of your jurisdiction, and any disputes relating
            to these terms will be subject to the exclusive jurisdiction of the courts located in your
            jurisdiction.`
          ]
        },
        {
          title: '10. Contact Information',
          paragraphs: [
            {
              text:
                'If you have any questions or concerns about these Terms of Use, please contact us at:',
              link: { label: 'info@emmanuelbaptistnc.org', href: 'mailto:info@emmanuelbaptistnc.org' }
            }
          ]
        }
      ]
    },

    privacy: {
      heading: 'Privacy Policy',
      sections: [
        {
          paragraphs: [
            `Your privacy is important to us. This website does not collect personal information or
            require users to create accounts. We gather minimal, anonymized analytics data (compliant
            with applicable privacy laws) solely to improve the site’s functionality and content.`
          ]
        },
        {
          paragraphs: [
            `We do not share, sell, or disclose any visitor data with third parties, except for
            analytics information collected in aggregate form. By using our website, you agree to
            this policy.`
          ]
        },
        {
          paragraphs: [
            {
              text: 'If you have any questions or concerns about this policy, contact us at:',
              link: { label: 'info@emmanuelbaptistnc.org', href: 'mailto:info@emmanuelbaptistnc.org' }
            }
          ]
        }
      ]
    }
  };

  // Utilities
  const formatDate = (iso?: string) =>
    iso ? new Date(iso).toLocaleDateString(undefined, { year: 'numeric', month: 'long', day: 'numeric' }) : '';
</script>

<!-- PAGE BACKGROUND / DECOR -->
<div class="relative grow pt-10 sm:pt-12 overflow-x-hidden space-y-8">
  <div aria-hidden="true" class="absolute inset-0 -z-10 bg-gradient-to-br from-sky-50 via-sky-50 to-white"></div>
  <div aria-hidden="true" class="pointer-events-none absolute inset-0 -z-10 opacity-40">
    <div class="absolute left-[-10%] top-10 h-48 w-80 blur-[106px] bg-gradient-to-br from-sky-200 to-sky-300"></div>
    <div class="absolute right-[-6%] top-28 h-36 w-72 blur-[106px] bg-gradient-to-r from-sky-200 to-sky-100"></div>
  </div>

  <!-- Header -->
  <section id="legal" class="w-full scroll-mt-28 py-8 md:py-12">
    <div class="mx-auto max-w-7xl px-6 md:px-12 xl:px-6">
      <h1 class="text-center text-4xl font-extrabold text-zinc-900 md:text-5xl">Legal</h1>
    </div>
  </section>

  <!-- Terms of Service -->
  <section id="terms-of-service" class="w-full scroll-mt-28 py-12 md:py-16">
    <div class="mx-auto w-full max-w-3xl px-6 text-center">
      <h2 class="border-b border-zinc-200 pb-6 text-2xl font-extrabold text-zinc-900 md:text-3xl">
        {legal.terms.heading}
      </h2>
      {#if legal.terms.updated}
        <p class="mt-8 mb-2 text-sm font-medium text-zinc-600">
          Posted {formatDate(legal.terms.updated)}
        </p>
      {/if}

      {#each legal.terms.sections as sec}
        {#if sec.title}
          <h3 class="mt-10 text-xl font-bold text-zinc-900 md:text-2xl">{sec.title}</h3>
        {/if}

        {#each sec.paragraphs as p}
          {#if typeof p === 'string'}
            <p class="mt-3 text-left text-lg leading-7 text-zinc-700">{p}</p>
          {:else}
            <p class="mt-3 text-left text-lg leading-7 text-zinc-700">
              {p.text}
              {#if p.link}
                <a class="font-semibold text-zinc-900 underline decoration-sky-300/60 underline-offset-2 hover:decoration-sky-400"
                  href={p.link.href}>{p.link.label}</a>
              {/if}
            </p>
          {/if}
        {/each}
      {/each}
    </div>
  </section>

  <!-- Privacy Policy -->
  <section id="privacy-policy" class="w-full scroll-mt-28 pb-16 md:pb-36">
    <div class="mx-auto w-full max-w-3xl px-6 text-center">
      <h2 class="border-b border-zinc-200 pb-6 text-2xl font-extrabold text-zinc-900 md:text-3xl">
        {legal.privacy.heading}
      </h2>

      {#each legal.privacy.sections as sec}
        {#if sec.title}
          <h3 class="mt-8 text-xl font-bold text-zinc-900 md:text-2xl">{sec.title}</h3>
        {/if}

        {#each sec.paragraphs as p}
          {#if typeof p === 'string'}
            <p class="mt-4 text-left text-lg leading-7 text-zinc-700">{p}</p>
          {:else}
            <p class="mt-4 text-left text-lg leading-7 text-zinc-700">
              {p.text}
              {#if p.link}
                <a class="font-semibold text-zinc-900 underline decoration-sky-300/60 underline-offset-2 hover:decoration-sky-400"
                  href={p.link.href}>{p.link.label}</a>
              {/if}
            </p>
          {/if}
        {/each}
      {/each}
    </div>
  </section>
</div>
