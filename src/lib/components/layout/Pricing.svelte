<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "The professional-grade AI platform for legal expertise",
		subtitle = "Flexible plans designed for law firms, in-house legal teams, and professional services. Every tier includes Harvey’s secure, domain-specific AI for legal work.",
		tierNames = ["Professional", "Business", "Enterprise"],
		features = [
			{
				name: "Best for",
				tiers: {
					Professional: "Pilot programs or small teams",
					Business: "Large legal teams or practice groups",
					Enterprise: "Organization-wide, advanced controls"
				}
			},
			{
				name: "Assistant (domain-specific AI)",
				tiers: {
					Professional: true,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Vault (secure document workspace)",
				tiers: {
					Professional: "Up to 1,000 docs per Vault",
					Business: "Up to 10,000 docs per Vault",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Knowledge (cited legal/tax research)",
				tiers: {
					Professional: true,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Workflows (AI-powered process automation)",
				tiers: {
					Professional: false,
					Business: "Prebuilt workflows",
					Enterprise: "Fully custom workflows"
				}
			},
			{
				name: "Legal DMS & SharePoint integrations",
				tiers: {
					Professional: false,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Microsoft Word add-in",
				tiers: {
					Professional: false,
					Business: true,
					Enterprise: true
				}
			},
			{
				name: "Security/compliance (SOC2, GDPR, SSO, audit logs)",
				tiers: {
					Professional: true,
					Business: true,
					Enterprise: "+ Data residency controls"
				}
			},
			{
				name: "Support",
				tiers: {
					Professional: "Email support",
					Business: "24/7 white glove support",
					Enterprise: "Dedicated CSM & enterprise support"
				}
			},
			{
				name: "Custom workflows & consulting",
				tiers: {
					Professional: false,
					Business: false,
					Enterprise: true
				}
			},
			{
				name: "Pricing",
				tiers: {
					Professional: "Contact sales",
					Business: "Contact sales",
					Enterprise: "Custom quote"
				}
			}
		],
		tiers = [
			{
				name: "Professional",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "For legal teams piloting Harvey or supporting a small group. Core domain-specific AI features with secure document analysis and cited research.",
				features: [
					"Domain-specific AI Assistant",
					"Analyze up to 1,000 docs per Vault",
					"Cited Knowledge research",
					"SOC2, GDPR, SSO, audit logs",
					"Email support"
				],
				cta: {
					label: "Request demo",
					href: "/contact"
				}
			},
			{
				name: "Business",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "For large practice groups or departments. Full Harvey platform, scalable Vaults, automated workflows, white glove onboarding, advanced integrations.",
				features: [
					"All Professional features",
					"Up to 10,000 docs per Vault",
					"Prebuilt AI Workflows",
					"Microsoft Word add-in",
					"DMS/SharePoint integrations",
					"24/7 white glove support"
				],
				cta: {
					label: "Request demo",
					href: "/contact"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "For firmwide or enterprise-wide deployment. Unlimited scale, full custom workflows, on-prem/data residency options, dedicated CSM, priority support, custom integrations.",
				features: [
					"All Business features",
					"Unlimited Vaults",
					"Fully custom workflows & consulting",
					"Data residency controls",
					"Dedicated CSM & priority SLAs",
					"Custom integrations"
				],
				cta: {
					label: "Contact sales",
					href: "/contact"
				}
			}
		]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;

	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-200 p-0.5 gap-0.5">
				<button
					class="rounded-full px-4 py-1.5 text-sm font-semibold transition-all duration-200 {!annual ? 'bg-white text-gray-900 shadow-sm' : 'text-gray-600 hover:text-gray-900'}"
					onclick={() => (annual = false)}
				>
					Monthly
				</button>
				<button
					class="rounded-full px-4 py-1.5 text-sm font-semibold transition-all duration-200 {annual ? 'bg-white text-gray-900 shadow-sm' : 'text-gray-600 hover:text-gray-900'}"
					onclick={() => (annual = true)}
				>
					Annual <span class="text-xs ml-1 text-gray-500">Save 20%</span>
				</button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />

<!--
Harvey supports the global legal teams at Comcast, Verizon, Microsoft, PwC, Adecco Group, Bridgewater, and over 250 leading firms and companies around the world.
The future of legal work is here—secure, scalable, client-ready. Start with the fully secure, audit-ready AI platform designed for legal and professional service leaders. Request a demo to see how Harvey can support your most trusted work.
-->
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
