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
	import IconTarget from "~icons/lucide/target";
	import IconRocket from "~icons/lucide/rocket";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
		{
			title: "Shape Market-Ready Products",
			description: "Work directly on products that help startups achieve product-market fit and secure funding rounds.",
			icon: IconTarget
		},
		{
			title: "Learn from Industry Leaders",
			description: "Gain insights from Sukrut's unique blend of design expertise and venture capital strategy thinking.",
			icon: IconUsers
		},
		{
			title: "Impact Early-Stage Innovation",
			description: "Help first-time founders transform ideas into investor-ready products that demonstrate real market traction.",
			icon: IconRocket
		}
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
			name: "David Chen",
			position: "Senior Product Designer",
			company: "Design Team",
			quote:
				"What drew me to Joshi Studio was the unique blend of design thinking and business strategy. Every project feels meaningful because we're helping founders build products that actually matter. The culture here celebrates both creative excellence and strategic impact.",
			image: "/generated/image-a-professional-headshot-of-an-asian-male.webp"
		},
		{
			name: "Amara Williams",
			position: "Product Strategy Lead",
			company: "Strategy Team",
			quote:
				"The growth opportunities here are incredible. I started as a junior strategist and now lead client relationships with pre-seed founders. Sukrut's mentorship and the team's investment in my development have been game-changing for my career.",
			image: "/generated/image-a-professional-headshot-of-a-black-femal.webp"
		},
		{
			name: "Carlos Rodriguez",
			position: "Senior Frontend Engineer",
			company: "Engineering Team",
			quote:
				"The work environment here strikes the perfect balance between high standards and collaboration. We build products that help startups secure funding and find product-market fit. There's nothing quite like seeing founders succeed because of the work we do together.",
			image: "/generated/image-a-professional-headshot-of-a-hispanic-ma.webp"
		}
	];

	const processSteps = [
		{
			step: 1,
			title: "Apply",
			description:
				"Submit your application with your resume and portfolio showcasing work that demonstrates strategic thinking and user empathy."
		},
		{
			step: 2,
			title: "Strategy Discussion",
			description: "Meet with Sukrut and the team to discuss your approach to balancing design excellence with business validation."
		},
		{
			step: 3,
			title: "Join the Mission",
			description: "Start helping first-time founders build investor-ready products that achieve real market traction."
		}
	];

	const values = [
		{
			icon: IconHeart,
			title: "Design Empathy",
			description: "We combine deep user understanding with strategic business thinking to create products that truly matter."
		},
		{
			icon: IconUsers,
			title: "Founder-Focused",
			description: "We're dedicated to helping first-time founders navigate the complex journey from idea to market-ready product."
		},
		{
			icon: IconGlobe,
			title: "VC-Aligned Strategy",
			description: "We understand what investors want and help startups build traction-ready products that secure funding."
		}
	];
</script>

<!-- Hero Section -->

<SecondaryHero
	title="Shape tomorrow's startups"
	subtitle="Work at the intersection of design and strategy to help pre-seed startups turn early ideas into market-ready products. Join our team of strategists, designers, and product experts who collaborate with driven founders to build what matters."
	imageSrc="/generated/image-a-creative-team-of-diverse-professionals.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="Shape the future of startup success" />

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
