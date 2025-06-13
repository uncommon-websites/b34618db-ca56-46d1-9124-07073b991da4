<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={true}
  title="Trusted by the world’s leading legal teams"
  subtitle="Harvey powers high-stakes work for top law firms and global enterprises, built with deep domain expertise and proven across complex legal systems."
  customers={[
    {
      name: "Olivia Martinez",
      position: "Partner, Litigation",
      imageSrc: "/generated/image-a-confident-female-legal-professional-wi.webp"
    },
    {
      name: "David Kim",
      position: "Chief Legal Officer",
      imageSrc: "/generated/image-a-professional-male-executive-in-a-sharp.webp"
    },
    {
      name: "Sophia Wang",
      position: "Director of Innovation",
      imageSrc: "/generated/image-a-female-innovation-leader-smiling-warml.webp"
    },
    {
      name: "James Patel",
      position: "Managing Attorney",
      imageSrc: "/generated/image-a-male-attorney-in-a-tailored-suit-stand.webp"
    },
    {
      name: "Claire Dubois",
      position: "Business Consultant",
      imageSrc: "/generated/image-a-female-business-consultant-standing-co.webp"
    }
  ]}
/>
<LogoScroller
	label="Trusted by industry leaders"
	logoUrls={[
    'https://logo.clearbit.com/pwc.com',
    'https://logo.clearbit.com/comcast.com',
    'https://logo.clearbit.com/verizon.com'
  ]}
/>

<Summary
	title="AI for legal professionals"
	text="Harvey provides domain-specific AI solutions for law firms, professional service providers, and Fortune 500 companies. Accelerate expert work in contract analysis, research, due diligence, compliance, and litigation—with industry-leading security, accuracy, and multilingual support."
/>

<Testimonials
	testimonials={[
		{
			name: "Mei Chen",
			position: "General Counsel",
			company: "Silkroad Holdings",
			quote:
				"Thanks to Harvey, our contract review times are down by 60%. This means our team spends less time on repetitive tasks and more on strategic legal advice. It’s made a tangible impact on our bottom line.",
			image: "/generated/image-a-confident-asian-businesswoman-in-a-sop.webp"
		},
		{
			name: "Kwame Mensah",
			position: "Head of Compliance",
			company: "Aegis Financial Group",
			quote:
				"With Harvey handling our compliance checks, we’ve reduced our audit risk and saved over $250,000 in potential legal fees this year alone. The peace of mind is invaluable.",
			image: "/generated/image-a-confident-black-male-executive-in-a-co.webp"
		},
		{
			name: "Camila Rivera",
			position: "Innovation Lead",
			company: "LexNova Partners",
			quote:
				"Harvey lets us deliver answers to complex client questions in half the time. Our client satisfaction scores have never been higher, and we’re taking on more business without expanding headcount.",
			image: "/generated/image-a-professional-latina-woman-in-a-corpora.webp"
		}
	]}
/>

<Features
  title="What makes Harvey different"
  subtitle="AI designed for the demands of legal and professional services, with results you can trust."
  features={[
    {
      title: "Domain-specific models",
      description: "Purpose-built AI that understands legal, regulatory, and tax work across global standards and 50+ jurisdictions."
    },
    {
      title: "Enterprise-grade security",
      description: "SOC2 Type II, ISO 27001, GDPR, and CCPA compliance, with zero customer data training and full control over data residency."
    },
    {
      title: "Document intelligence",
      description: "Upload, store, and analyze thousands of documents instantly—extract key terms, review deal points, and access your firm’s internal knowledge."
    },
    {
      title: "AI assistant for legal workflows",
      description: "Delegate complex drafting, due diligence, and research with a personal assistant fluent in legal and business tasks."
    },
    {
      title: "Cited and up-to-date answers",
      description: "Get grounded results from trusted sources, with accurate citations and knowledge updated regularly across jurisdictions."
    },
    {
      title: "24/7 expert support",
      description: "Rely on a dedicated team with experience supporting the world’s most demanding legal and enterprise environments."
    }
  ]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Accelerate contract review",
			description: "Analyze and summarize contracts in seconds. Harvey detects key risks, surfaces deal points, and highlights unusual terms—letting your team focus on negotiation, not paperwork.",
			image: "/generated/image-a-diverse-group-of-lawyers-gathered-arou.webp",
			link: {
				href: "/use-cases/contract-review",
				label: "Learn more"
			}
		},
		{
			title: "Automate due diligence",
			description: "Review hundreds of documents in a fraction of the time. Harvey helps legal teams quickly extract critical information from data rooms, find red flags, and generate comprehensive due diligence reports.",
			image: "/generated/image-a-corporate-team-sitting-around-a-confer.webp",
			link: {
				href: "/use-cases/due-diligence",
				label: "Learn more"
			}
		},
		{
			title: "Stay ahead on compliance",
			description: "Track new regulations and automate compliance mapping. Harvey delivers up-to-date, cited insights so your in-house team can respond faster to global legal changes—with confidence.",
			image: "/generated/image-an-in-house-legal-team-in-a-sleek-modern.webp",
			link: {
				href: "/use-cases/compliance-management",
				label: "Learn more"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction
  title="Empower your legal team to move faster"
  subtitle="AI built for professionals, trusted by leaders"
  description="See how 28+ AmLaw 100 firms, global enterprises, and top innovators accelerate workflows, reduce busywork, and deliver more value for every client—with enterprise security and full control. Ready to see results?"
  imageSrc="/generated/image-a-happy-and-confident-professional-legal.webp"
  callsToAction={[
    { href: "/demo", label: "Request a demo", variant: "primary" },
    { href: "/contact", label: "Talk to sales", variant: "secondary" }
  ]}
/>
