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
		title = "Milestone-based pricing for startup success",
		subtitle = "Build investor-ready products with VC-aligned strategy and design validation",
		tierNames = ["MVP Validation", "Product-Market Fit", "Scale & Growth"],
		features = [
			{
				name: "User research & validation",
				tiers: {
					"MVP Validation": "Basic interviews",
					"Product-Market Fit": "In-depth research",
					"Scale & Growth": "Advanced research"
				}
			},
			{
				name: "Strategic design framework",
				tiers: {
					"MVP Validation": "Core framework",
					"Product-Market Fit": "Full framework",
					"Scale & Growth": "Enterprise framework"
				}
			},
			{
				name: "Investor-ready prototypes",
				tiers: {
					"MVP Validation": "Low-fidelity",
					"Product-Market Fit": "High-fidelity",
					"Scale & Growth": "Production-ready"
				}
			},
			{
				name: "Market validation testing",
				tiers: {
					"MVP Validation": true,
					"Product-Market Fit": true,
					"Scale & Growth": true
				}
			},
			{
				name: "VC pitch deck design",
				tiers: {
					"MVP Validation": false,
					"Product-Market Fit": true,
					"Scale & Growth": true
				}
			},
			{
				name: "Business model validation",
				tiers: {
					"MVP Validation": "Basic",
					"Product-Market Fit": "Advanced",
					"Scale & Growth": "Full strategy"
				}
			},
			{
				name: "Weekly strategy sessions",
				tiers: {
					"MVP Validation": "Bi-weekly",
					"Product-Market Fit": "Weekly",
					"Scale & Growth": "2x weekly"
				}
			},
			{
				name: "Founder coaching",
				tiers: {
					"MVP Validation": false,
					"Product-Market Fit": "Basic",
					"Scale & Growth": "Advanced"
				}
			},
			{
				name: "Post-launch support",
				tiers: {
					"MVP Validation": "30 days",
					"Product-Market Fit": "90 days",
					"Scale & Growth": "6 months"
				}
			}
		],
		tiers = [
			{
				name: "MVP Validation",
				monthlyPrice: 5000,
				yearlyPrice: null,
				description: "Validate your idea before you build. Perfect for pre-seed founders who need strategic direction.",
				features: [
					"Market research & user validation",
					"Core product strategy framework", 
					"Low-fidelity wireframes & prototypes",
					"Business model validation",
					"Bi-weekly strategy sessions",
					"30 days post-launch support"
				],
				cta: {
					label: "Start validation",
					href: "/contact?plan=mvp"
				}
			},
			{
				name: "Product-Market Fit",
				monthlyPrice: 12000,
				yearlyPrice: null,
				description: "Build investor-ready products with proven market traction for funding rounds.",
				features: [
					"In-depth user research & testing",
					"Full strategic design framework",
					"High-fidelity prototypes & designs",
					"VC pitch deck design & strategy",
					"Weekly founder strategy sessions",
					"Basic founder coaching",
					"90 days post-launch support"
				],
				cta: {
					label: "Get funded",
					href: "/contact?plan=pmf"
				},
				highlight: true
			},
			{
				name: "Scale & Growth",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Scale your validated product to 50+ funded portfolio companies with enterprise strategy.",
				features: [
					"Advanced market research & analytics",
					"Enterprise-grade design system",
					"Production-ready development handoff",
					"Full growth strategy & roadmap",
					"2x weekly strategic sessions",
					"Advanced founder & team coaching",
					"6 months ongoing support",
					"Portfolio company network access"
				],
				cta: {
					label: "Scale together",
					href: "/contact?plan=scale"
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
	let annual = $state(false); // Project-based pricing, not subscription
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-center justify-center text-center mb-12">
		<SectionHeader {title} {subtitle} />
		<p class="text-body text-emphasis-medium mt-4 max-w-3xl">
			Milestone-based pricing means you only pay when we hit key validation checkpoints. No monthly subscriptions, no hidden fees. Pay for results, not retainers.
		</p>
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
								value={tier.monthlyPrice}
								suffix=" project"
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
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
