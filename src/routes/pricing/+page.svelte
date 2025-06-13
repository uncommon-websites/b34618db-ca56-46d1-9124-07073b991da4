<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
  testimonials={[
    {
      name: "Lina Zhu",
      position: "Head of Innovation",
      company: "Wang & Han LLP",
      quote:
        "With Harvey, we reduced contract review time by over 40%. The ROI was clear in just weeks—our teams now focus on strategic, high-impact work instead of repetitive review.",
      image: "/generated/image-a-professional-headshot-of-an-east-asian.webp"
    },
    {
      name: "Kwame Johnson",
      position: "Director of Legal Technology",
      company: "Meridian Law Group",
      quote:
        "Harvey's interface is so intuitive that our attorneys adopted it firm-wide in days—not months. Integrating with our document management was effortless.",
      image: "/generated/image-a-professional-headshot-of-a-black-man-l.webp"
    },
    {
      name: "Valeria Mendoza",
      position: "Associate General Counsel",
      company: "Cortech Industries",
      quote:
        "The support team at Harvey is unmatched. Getting set up was painless, and we’re consistently seeing smarter outputs and faster turnaround. Worth every dollar.",
      image: "/generated/image-a-professional-headshot-of-a-latina-woma.webp"
    }
  ]}
/>

<CallToAction
  title="Lead with AI that delivers"
  subtitle="Join 250+ organizations and 45,000+ professionals—Harvey helps legal and enterprise teams work faster, with less risk and higher-quality results."
  description="Harvey automates critical but time-consuming legal tasks—so your team can focus on strategy, not repetition. Built exclusively for the legal world, Harvey delivers precise, cited results, enterprise security, and 24/7 support. See why 28 AmLaw 100 firms and global leaders choose Harvey to get more done, with less risk."
  imageSrc="/generated/image-a-cheerful-legal-professional-in-a-moder.webp"
  callsToAction={[
    { href: '/signup', label: 'Start your free trial', variant: 'primary' },
    { href: '/contact', label: 'Talk to the Harvey team', variant: 'secondary' }
  ]}
/>

