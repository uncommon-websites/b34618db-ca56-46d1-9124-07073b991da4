<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Innovation",
			description: "Constantly challenging the status quo to create better solutions."
		},
		{
			title: "Integrity",
			description: "Building trust through transparent actions and honest communication."
		},
		{
			title: "Impact",
			description: "Measuring our success by the positive change we create for our clients."
		}
	];
</script>

<SecondaryHero
	title="The AI engine for legal work"
	subtitle="Trusted by top firms to drive speed, scale, and accuracy"
	imageSrc="/mockups/airport-screen-1749808867003.png"
/>

<!-- Story Section -->
<Story
  paragraphs={[
    "Harvey started with a simple idea: technology should actually understand professional work. Co-founders Winston Weinberg, a former litigator, and Gabe Pereyra, a former research scientist at DeepMind, set out to build AI tools made for legal experts—not just technologists.",
    "From day one, Harvey's focus has been practical: help legal teams move faster, with more confidence and less guesswork. Since launch, more than 250 organizations—from leading law firms to Fortune 500 companies—have adopted Harvey because it fits the real-world pace of complex legal work and supports over 50 languages and jurisdictions.",
    "Harvey was built for enterprise trust and reliability. With industry-leading security, zero training on customer data, and 24/7 expert support, professionals around the world depend on Harvey to keep their work accurate, secure, and efficient."
  ]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
  stakeholderType="team"
  title="Our team."
  subtitle="Built by legal and AI experts."
  stakeholders={[
    {
      name: "Winston Weinberg",
      position: "CEO & Co-Founder",
      bio:
        "Former litigator at O'Melveny with a focus on complex commercial disputes. Leads Harvey’s direction at the intersection of law and applied technology.",
      image: "/generated/image-a-portrait-of-a-male-founder-with-a-prof.webp"
    },
    {
      name: "Gabe Pereyra",
      position: "President & Co-Founder",
      bio:
        "Former research scientist at DeepMind with a background in large-scale machine learning and model architecture design for high-stakes domains.",
      image: "/generated/image-a-headshot-of-a-male-founder-showcasing-.webp"
    }
  ]}
/>

<StakeholderGrid
  stakeholderType="investor"
  title="Backed by leading investors."
  subtitle="Series D led by Sequoia Capital"
  stakeholders={[
    {
      name: "Sequoia Capital",
      image: "https://cdn.brandfetch.io/sequoiacap.com/w/400/h/400/logo"
    }
  ]}
/>

<!-- CTA Section -->
<CallToAction
  title="Build with Harvey"
  subtitle="Redefining expert work with domain-specific AI"
  description="Harvey is redefining expert work with domain-specific AI—making legal and professional teams faster, sharper, and more impactful around the world. With over 45,000 professionals using Harvey across 44 countries and in 50+ languages, we’re growing quickly—and intentionally.\n\nJoin a world-class team of builders, lawyers, researchers, and engineers helping Fortune 500 companies and industry-leading firms work in entirely new ways. If you’re driven to solve hard problems and excited to shape how expertise scales globally, we want to work with you.\n\nHarvey partners with forward-thinking firms and organizations to deploy powerful, secure, enterprise-grade AI that delivers lasting value. From law firms to tech platforms to global in-house teams, we co-create solutions that change how business gets done."
  callsToAction={[
    { href: "/careers", label: "Explore careers", variant: "primary" },
    { href: "/partner", label: "Partner with us", variant: "secondary" }
  ]}
/>
