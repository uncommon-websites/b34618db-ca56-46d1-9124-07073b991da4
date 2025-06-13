<script lang="ts">
	// Types

	// Components
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Card from "$lib/components/ui/Card.svelte";
	import JobList, { type JobOpening } from "./JobList.svelte";

	// Icons
	import IconBriefcase from "~icons/lucide/briefcase";
	import IconUsers from "~icons/lucide/users";
	import IconHeart from "~icons/lucide/heart";
	import IconGlobe from "~icons/lucide/globe";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
  {
    title: "Impact at scale",
    description:
      "Serve leading law firms, Fortune 500s, and 45,000+ professionals in 44+ countries.",
    icon: IconGlobe,
  },
  {
    title: "Growth and learning",
    description:
      "Access mentorship, an annual professional development stipend, and direct collaboration with world-class experts.",
    icon: IconUsers,
  },
  {
    title: "Comprehensive support",
    description:
      "Full medical, dental, and vision; paid parental leave; daily office meals; flexible time off; and a competitive 401(k) match.",
    icon: IconHeart,
  },
];

	const openings: JobOpening[] = [
		// Engineering
		{
			title: "Senior Frontend Developer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Backend Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Design Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Design
		{
			title: "UX/UI Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Product
		{
			title: "Product Manager",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Analyst",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Marketing
		{
			title: "Marketing Specialist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Content Strategist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Social Media Manager",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		}
	];

	const employeeTestimonials = [
  {
    name: "Michael Chen",
    position: "Senior Developer",
    company: "Engineering Team",
    quote:
      "At Harvey, you feel the energy of a team that values your ideas. I love the culture of collaboration—everyone genuinely wants you to succeed, and that motivates me to do my best work every day.",
    image:
      "/generated/image-a-professional-headshot-of-an-asian-male.webp"
  },
  {
    name: "Priya Sharma",
    position: "Product Designer",
    company: "Design Team",
    quote:
      "Joining Harvey has been a turning point for my growth. There are so many opportunities to learn across disciplines, and leadership encourages you to take on new challenges—you’re never stuck in one lane.",
    image:
      "/generated/image-a-professional-headshot-of-a-south-asian.webp"
  },
  {
    name: "Marcus Johnson",
    position: "Marketing Lead",
    company: "Marketing Team",
    quote:
      "The work environment here is welcoming, fast-paced, and inspiring. We celebrate big wins as a team, but it’s the everyday support and open feedback that really set Harvey apart.",
    image:
      "/generated/image-a-professional-headshot-of-a-black-male-.webp"
  }
];


	const processSteps = [
  {
    step: 1,
    title: "Apply online",
    description:
      "Submit your resume and answer a few role-specific questions—no formal cover letter required.",
  },
  {
    step: 2,
    title: "Intro call",
    description:
      "Connect with our recruiter for an overview of Harvey, your experience, and your interests. Get answers to your questions early.",
  },
  {
    step: 3,
    title: "Skills & culture interviews",
    description:
      "Meet team members for role-relevant discussions. Technical talent may complete a practical challenge; all interviews include time for your questions.",
  },
  {
    step: 4,
    title: "Offer & onboarding",
    description:
      "Receive feedback quickly—within a week in most cases. If you join us, we offer a comprehensive and personalized onboarding experience.",
  },
];

	const values = [
  {
    icon: IconHeart,
    title: "Excellence & rigor",
    description:
      "We're committed to expert-level work, high standards, and ongoing learning—because details matter in our field.",
  },
  {
    icon: IconUsers,
    title: "Collaboration & inclusion",
    description:
      "We support each other, embrace diversity of background and thought, and tackle challenges together—no one works alone at Harvey.",
  },
  {
    icon: IconGlobe,
    title: "Global perspective",
    description:
      "With teams and customers in 50+ countries, we value cultural context, continuous feedback, and sharing knowledge across borders.",
  },
  {
    icon: IconBriefcase,
    title: "Customer-first mindset",
    description:
      "We approach every challenge with white-glove service, responsiveness, and direct access to decision-makers.",
  },
];
</script>

<!-- Hero Section -->

<SecondaryHero
	title="Advance legal mastery through AI collaboration"
	subtitle="Grow with a team driving real change in law and technology"
	imageSrc="/generated/image-a-bright-modern-office-with-a-diverse-te.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="Build your career while making an impact" />

	<div class="mt-16 grid gap-4 md:grid-cols-3">
		{#each benefits as benefit}
			<Card {...benefit} />
		{/each}
	</div>
</section>

<!-- Culture Section -->
<Culture {values} />

<Testimonials testimonials={employeeTestimonials} />

<!-- Application Process -->
<section class={SECTION_BASE_CLASSES}>
	<div class="mx-auto">
		<h2 class="text-title1 mb-16">Our application process</h2>

		<div class="grid gap-12 md:grid-cols-3">
			{#each processSteps as { step, title, description }, i}
				<div class="flex flex-col">
					<div class="{ICON_CONTAINER_CLASSES} mb-6 size-11">
						<span class="text-headline">{step}</span>
					</div>
					<h3 class="text-headline mb-3">{title}</h3>
					<p class="text-body text-emphasis-low">{description}</p>
				</div>
			{/each}
		</div>
	</div>
</section>
<!-- Current Openings Section -->
<section class={GRADIENT_BG_CLASSES}>
	<div class="section-px section-py container mx-auto grid w-full items-start lg:grid-cols-2">
		<SectionHeader title="Current openings" subtitle="Find your perfect role" />

		<JobList {openings} />
	</div>
</section>
