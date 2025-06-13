<script lang="ts">
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import { animate, stagger } from "motion";
	import { onMount } from "svelte";

	// Types
	export type Value = {
		title: string;
		description: string;
	};

	// Props
	const { values = [] }: { values: Value[] } = $props();

	let cards: HTMLElement[] = $state([]);

	onMount(() => {
		if (!cards.length) return;
		if (window.self !== window.top) return;

		animate(
			cards,
			{
				y: ["1.5rem", 0],
				filter: ["blur(2px)", "blur(0px)"],
				opacity: [0, 1]
			},
			{
				duration: 0.3,
				ease: "easeOut",
				delay: stagger(0.1, {
					ease: "easeInOut"
				})
			}
		);
	});
</script>

<section class="bg-white dark:bg-gray-950">
	<div
		class="section-py section-px container mx-auto grid gap-8 [--gap:--spacing(8)] [--radius:var(--radius-2xl)]"
	>
		<!-- Updated Harvey culture section -->
<SectionHeader title="Redefining expert work—together" subtitle="A culture where mastery meets impact" />

<div class="mb-6">
  <div class="text-body text-gray-800 dark:text-gray-200 mb-8">
    At Harvey, we believe transformative technology starts with exceptional people. We're building more than AI for professionals—we’re building a high-performance culture where legal expertise meets technical excellence, and mastery drives impact every day.
  </div>

  <div class="text-title2 mb-2">We act with ownership. We build with purpose.</div>
  <div class="text-body text-gray-700 dark:text-gray-300 mb-8">
    Our culture is rooted in ambition and trust. We operate with a growth mindset, a bias for action, and accountability at every level. Every team member—across legal, engineering, research, operations, and design—plays an active role in shaping how the world works with professional AI.
  </div>

  <div class="text-title2 mb-2">Values we honor—and live by</div>
  <ul class="mb-8 list-disc ml-6 text-body text-gray-600 dark:text-gray-400">
    <li><b>Mastery over mediocrity:</b> We pursue depth, precision, and expert-quality outcomes in everything we do.</li>
    <li><b>Impact with integrity:</b> We move fast, but responsibly—engineers, lawyers, researchers, and business leaders all share in producing real, measurable outcomes for our users.</li>
    <li><b>Responsible innovation:</b> We build with principles. From model development to deployment, we balance experimentation with rigorous safeguards, security, and transparency.</li>
    <li><b>Transparency by default:</b> We share what we’re working on, challenge each other directly, and stay close to the customer voice. Truth travels fast here—especially when it leads to better decisions.</li>
    <li><b>Collaboration without compromise:</b> Our best ideas cut across domains. We champion expertise, share knowledge freely, and build software in partnership—always.</li>
    <li><b>Growth mindset:</b> We sharpen skills through feedback, iteration, and ambition. We celebrate high standards—not perfection—and improve every day.</li>
    <li><b>Diversity and inclusion:</b> Our platform is multilingual, global, and used by professionals in dozens of countries. Our team reflects that same depth of talent, perspective, and lived experience—and we’re better for it.</li>
  </ul>

  <div class="text-title2 mb-2">Where high trust meets high expectation</div>
  <div class="text-body text-gray-700 dark:text-gray-300 mb-8">
    We take our mission seriously: accelerate professional mastery through world-class AI systems. That makes Harvey both a hard and an exciting place to work. You’ll push your craft further than before—in a team that challenges you, supports you, and shares the urgency to build what lasting excellence looks like.
  </div>

  <div class="text-title2 mb-2">What we offer</div>
  <ul class="mb-8 list-disc ml-6 text-body text-gray-600 dark:text-gray-400">
    <li>24/7 customer support and in-house operational excellence—because empowered teams build faster</li>
    <li>Daily lunch and dinner provided in-office</li>
    <li>Comprehensive health, dental, and vision insurance</li>
    <li>Competitive retirement plan with company 401(k) match</li>
    <li>Paid parental leave</li>
    <li>Professional development stipend and annual learning budget</li>
    <li>State bar fee reimbursement for legal professionals</li>
    <li>Flexible paid time off policy</li>
  </ul>

  <div class="text-title2 mb-2">Build what's next—with us</div>
  <div class="text-body">
    Harvey is for those who want to move the needle—in law, software, machine learning, and what work itself can become. We're hiring across legal, technical, and operational functions, and we’re always looking for people hungry to shape defining tools built to last. If that sounds like you, we’d love to meet.
  </div>
  <div class="mt-6">
    <a class="text-button font-bold underline" href="/careers">View open roles</a>
  </div>
</div>
	</div>
</section>
