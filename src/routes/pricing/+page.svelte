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
			name: "Amara Okafor",
			position: "CEO & Co-Founder",
			company: "FlowMetrics",
			quote:
				"Joshi Studio's $5K investment saved us 6 months and $200K in development costs. We got our Series A because investors saw real traction, not just a pretty prototype.",
			image: "/generated/image-a-confident-black-woman-ceo-dressed-in-a.webp"
		},
		{
			name: "Diego Hernandez",
			position: "CTO & Co-Founder",
			company: "DataBridge",
			quote:
				"The milestone-based pricing was perfect for our pre-seed budget. We validated our MVP in 8 weeks and raised our first $500K round with 10x user engagement metrics.",
			image: "/generated/image-a-hispanic-man-cto-wearing-a-smart-casua.webp"
		},
		{
			name: "Kenji Nakamura",
			position: "Founder",
			company: "PulseAI",
			quote:
				"Most design agencies wanted $50K upfront. Joshi Studio's strategic approach meant we only built features users actually wanted. Our CAC dropped 70% post-launch.",
			image: "/generated/image-an-asian-woman-founder-elegantly-dressed.webp"
		}
	]}
/>

<CallToAction
	title="Ready to build your investor-ready MVP?"
	subtitle="Join 50+ funded portfolio companies"
	description="Stop wasting months building features users don't want. Get strategic validation before development begins and transform your early-stage idea into a market-ready product that investors actually fund."
	imageSrc="/generated/image-a-cheerful-startup-founder-is-seated-at-.webp"
	callsToAction={[
		{
			href: "/contact",
			label: "Start with MVP validation",
			variant: "primary"
		},
		{
			href: "/contact",
			label: "Schedule strategy call",
			variant: "secondary"
		}
	]}
/>
