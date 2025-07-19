<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import Hero from "$lib/components/layout/hero-sections/Hero.svelte";
	import UseCases from "$lib/components/layout/UseCases.svelte";
</script>

<Hero
	title="Turn your startup idea into an investor-ready product"
	subtitle="VC-aligned strategy meets design empathy to build products that demonstrate clear market traction from day one."
	imageSrc="/generated/image-a-group-of-young-startup-founders-are-ga.webp"
	centered={false}
/>
<LogoScroller 
	label="Trusted by ambitious startups" 
	logoUrls={[
		'https://logo.clearbit.com/notion.so',
		'https://logo.clearbit.com/airtable.com',
		'https://logo.clearbit.com/typeform.com',
		'https://logo.clearbit.com/vercel.com'
	]}
/>

<Summary
	title="What we do"
	text="We transform early-stage startup ideas into investor-ready products by combining VC-aligned strategy with design empathy. Starting at $5K, we help first-time founders build products that demonstrate clear market traction before development begins."
/>

<Testimonials
	testimonials={[
		{
			name: "Elyana Rodriguez",
			position: "Founder & CEO",
			company: "Reglow",
			quote:
				"Joshi Studio saved us 3 months of build time and $45K in development costs by validating our core assumptions before we wrote a single line of code. We raised our pre-seed round based on their prototype alone.",
			image: "/generated/image-a-professional-female-founder-in-her-30s.webp"
		},
		{
			name: "Marcus Tran",
			position: "Co-founder",
			company: "StitchAI",
			quote:
				"Instead of burning 6 months building features nobody wanted, we spent 3 weeks with Joshi Studio understanding what investors actually look for. The clarity was worth every penny of our $12K investment.",
			image: "/generated/image-a-male-entrepreneur-in-his-40s-wearing-a.webp"
		},
		{
			name: "Zara Okafor",
			position: "Founder",
			company: "FlowMetrics",
			quote:
				"Working with Sukrut eliminated the guesswork that kills most startups. We avoided costly pivots and launched with investor-ready traction metrics. ROI was 400% within our first funding round.",
			image: "/generated/image-a-young-professional-woman-in-her-late-2.webp"
		}
	]}
/>

<UseCases
	title="Use Cases"
	subtitle="How we help first-time founders build investor-ready products"
	useCases={[
		{
			title: "Validate your MVP before you build",
			description: "Before writing code or hiring developers, test your riskiest assumptions with real users. Our validation process saves months of development time and prevents costly pivots by proving demand exists for your core value proposition.",
			image: "/generated/image-a-group-of-first-time-startup-founders-g.webp",
			link: {
				href: "/use-cases/mvp-validation",
				label: "Learn more"
			}
		},
		{
			title: "Build investor-ready traction metrics",
			description: "Transform your startup idea into compelling evidence that VCs want to see. We help you create measurable proof of product-market fit through strategic user research, competitive positioning, and clear growth indicators.",
			image: "/generated/image-in-a-sleek-modern-boardroom-a-group-of-e.webp",
			link: {
				href: "/use-cases/investor-readiness",
				label: "Learn more"
			}
		},
		{
			title: "De-risk product strategy with user insights", 
			description: "Stop building features nobody wants. Our user research process uncovers what your target market actually needs, helping you prioritize the right features that drive adoption and retention from day one.",
			image: "/generated/image-a-product-strategist-sitting-in-a-relaxe.webp",
			link: {
				href: "/use-cases/product-strategy",
				label: "Learn more"
			}
		}
	]}
/>

<Features
	title="Why founders choose Joshi Studio"
	subtitle="We combine design empathy with VC-aligned strategy to build products that demonstrate clear market traction"
	features={[
		{
			title: "MVP validation that proves demand",
			description:
				"Test your riskiest assumptions fast and get user feedback before you write a single line of code."
		},
		{
			title: "VC-aligned product strategy",
			description:
				"Bridge the gap between what you want to build and what investors want to see—traction, clarity, and demand."
		},
		{
			title: "Design that drives business results",
			description:
				"Every UX and UI decision is based on user needs and business goals, not just aesthetics."
		},
		{
			title: "Market traction before development",
			description:
				"Validate your value proposition with real users and create compelling evidence of product-market fit."
		},
		{
			title: "Milestone-based pricing for startups",
			description:
				"Start at $5K for MVP validation with flexible scope that grows with your funding stage."
		},
		{
			title: "50+ funded portfolio companies",
			description:
				"Proven track record helping early-stage teams launch with clarity and secure investment faster."
		}
	]}
/>
<AboutTeaser />
<CallToAction
	title="Ready to build an investor-ready product?"
	subtitle="Get started with Joshi Studio"
	description="Stop wasting months building features users don't want. Let's validate your startup idea and create a product that demonstrates clear market traction before development begins."
	imageSrc="/generated/image-a-cheerful-startup-founder-with-a-friend.webp"
	callsToAction={[
		{
			href: "/contact",
			label: "Start validation project",
			variant: "primary"
		},
		{
			href: "/about",
			label: "Learn our process",
			variant: "secondary"
		}
	]}
/>
