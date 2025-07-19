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
			title: "Design empathy",
			description: "Understanding user needs deeply before building anything, ensuring products solve real problems."
		},
		{
			title: "Business validation",
			description: "Combining design expertise with VC-aligned strategy to create investor-ready products."
		},
		{
			title: "Founder focus",
			description: "Helping first-time founders avoid product-market fit pitfalls through strategic direction."
		}
	];
</script>

<SecondaryHero
	title="Bridging design empathy with business validation"
	subtitle="Transforming early-stage ideas into investor-ready products"
	imageSrc="/generated/image-a-professional-design-team-working-colla.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Sukrut's journey began watching brilliant founders waste months building features users didn't want. Despite having game-changing ideas, too many pre-seed startups struggled to demonstrate market traction to investors because they lacked strategic direction from day one.",
		"The lightbulb moment came from combining deep UX design expertise with venture capital insights. Most design agencies create beautiful products, but miss the crucial step of validating business assumptions before development begins. Joshi Studio bridges this gap by delivering VC-aligned strategy that ensures every design decision supports investor readiness.",
		"Today, we help first-time founders transform early-stage ideas into market-ready products that demonstrate clear traction. Our milestone-based approach starting at $5K makes strategic design accessible to pre-seed startups, proving that with the right combination of design empathy and business validation, founders can avoid common product-market fit pitfalls and build something investors actually want to fund."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Meet the founder."
	subtitle="Your partner in building investor-ready products."
	stakeholders={[
		{
			name: "Sukrut Joshi",
			position: "Founder & Design Strategist",
			bio: "Combines product strategy expertise with UX design roots and deep venture capital knowledge, giving unique insight into what investors want and how to build traction-ready products.",
			image: "/generated/image-a-professional-headshot-of-a-confident-m.webp"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
	title="Ready to build something investors want?"
	subtitle="Transform your idea into market-ready product"
	description="Join the first-time founders already leveraging our VC-aligned strategy to validate their ideas and demonstrate clear market traction. Starting at $5K for MVP validation."
/>
