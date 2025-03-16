<!-- components/Profile.svelte -->
<script>
	import { onMount } from 'svelte';

	const socialLinks = [
		{ name: 'Ja Ela, Sri Lanka', icon: 'map-pin', href: 'https://g.co/kgs/CzdkRpT' },
		{ name: 'Email', icon: 'mail', href: 'mailto:nethbotheju@gmail.com' },
		// { name: 'ResearchGate', icon: 'book', href: '#' },
		{ name: 'Twitter', icon: 'twitter', href: 'https://twitter.com/wsnethbotheju' },
		{ name: 'LinkedIn', icon: 'linkedin', href: 'https://www.linkedin.com/in/nethbotheju/' },
		// { name: 'Instagram', icon: 'instagram', href: '#' },
		{ name: 'Github', icon: 'github', href: 'https://github.com/nethbotheju' }
		// { name: 'Google Scholar', icon: 'book-open', href: '#' }
	];

	let showSocialLinks = false;

	function toggleSocialLinks() {
		showSocialLinks = !showSocialLinks;
	}
</script>

<section class="mb-8">
	<!-- Desktop View (≥ 1024px) -->
	<div class="mb-6 hidden lg:block">
		<div class="mr-6 mb-4 h-24 w-24 flex-shrink-0 md:mb-0">
			<img
				src="/profilePic.jpg"
				alt="Neth Pehesara Botheju"
				class="h-full w-full rounded-full object-cover shadow"
			/>
		</div>
		<div>
			<h1 class="mb-1 text-2xl font-bold text-gray-800">Neth Pehesara Botheju</h1>
			<p class="mb-4 text-sm text-gray-600">
				Second-year Computer Science student at the University of Westminster. Passionate about
				software development, backend technologies, and AI/ML. Dedicated to innovation, efficiency,
				and solving real-world problems through technology.
			</p>
			<div class="grid-row grid gap-2">
				{#each socialLinks as link}
					<a href={link.href} class="flex items-center text-sm text-gray-600 hover:text-blue-500">
						<span class="mr-2 h-4 w-4">
							<svg
								class="h-full w-full"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							>
								<!-- SVG paths remain unchanged -->
								<!-- Update this in all SVG conditional blocks throughout the component -->
								{#if link.icon === 'map-pin'}
									<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
									<circle cx="12" cy="10" r="3"></circle>
								{:else if link.icon === 'mail'}
									<path
										d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
									></path>
									<polyline points="22,6 12,13 2,6"></polyline>
								{:else if link.icon === 'twitter'}
									<path
										d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"
									></path>
								{:else if link.icon === 'linkedin'}
									<path
										d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
									></path>
									<rect x="2" y="9" width="4" height="12"></rect>
									<circle cx="4" cy="4" r="2"></circle>
								{:else if link.icon === 'github'}
									<path
										d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
									></path>
								{/if}
							</svg>
						</span>
						{link.name}
					</a>
				{/each}
			</div>
		</div>
	</div>

	<!-- Tablet View (≥ 500px and < 1024px) -->
	<div class="mb-6 hidden sm:flex md:flex lg:hidden">
		<div class="flex w-full flex-row items-start space-x-4">
			<div class="h-20 w-20 flex-shrink-0">
				<img
					src="/profilePic.jpg"
					alt="Neth Pehesara Botheju"
					class="h-full w-full rounded-full object-cover shadow"
				/>
			</div>
			<div class="flex-1">
				<h1 class="mb-1 text-xl font-bold text-gray-800">Neth Pehesara Botheju</h1>
				<p class="mb-4 text-sm text-gray-600">
					Second-year Computer Science student at the University of Westminster. Passionate about
					software development, backend technologies, and AI/ML.
				</p>
				<div class="grid grid-cols-2 gap-2">
					{#each socialLinks as link}
						<a href={link.href} class="flex items-center text-sm text-gray-600 hover:text-blue-500">
							<span class="mr-2 h-4 w-4">
								<svg
									class="h-full w-full"
									viewBox="0 0 24 24"
									fill="none"
									stroke="currentColor"
									stroke-width="2"
									stroke-linecap="round"
									stroke-linejoin="round"
								>
									<!-- SVG icons remain the same -->
									<!-- Update this in all SVG conditional blocks throughout the component -->
									{#if link.icon === 'map-pin'}
										<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
										<circle cx="12" cy="10" r="3"></circle>
									{:else if link.icon === 'mail'}
										<path
											d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
										></path>
										<polyline points="22,6 12,13 2,6"></polyline>
									{:else if link.icon === 'twitter'}
										<path
											d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"
										></path>
									{:else if link.icon === 'linkedin'}
										<path
											d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
										></path>
										<rect x="2" y="9" width="4" height="12"></rect>
										<circle cx="4" cy="4" r="2"></circle>
									{:else if link.icon === 'github'}
										<path
											d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
										></path>
									{/if}
								</svg>
							</span>
							{link.name}
						</a>
					{/each}
				</div>
			</div>
		</div>
	</div>

	<!-- Small Mobile View (< 500px) -->
	<div class="flex items-center justify-between sm:hidden">
		<div class="flex items-center">
			<div class="mr-3 h-16 w-16">
				<img
					src="/profilePic.jpg"
					alt="Neth Pehesara Botheju"
					class="h-full w-full rounded-full object-cover shadow"
				/>
			</div>
			<div>
				<h1 class="text-lg font-bold text-gray-800">Neth Pehesara Botheju</h1>
				<p class="text-xs text-gray-600">
					Second-year Computer Science student at the University of Westminster.
				</p>
			</div>
		</div>
		<button
			class="rounded-md bg-blue-500 px-3 py-1 text-sm text-white"
			on:click={toggleSocialLinks}
		>
			Follow
		</button>
	</div>

	<!-- Mobile Social Links Dropdown (only for small screens) -->
	{#if showSocialLinks}
		<div class="mt-4 rounded-md bg-gray-50 p-4 shadow-md sm:hidden">
			<div class="grid grid-cols-2 gap-2">
				{#each socialLinks as link}
					<a href={link.href} class="flex items-center text-sm text-gray-600 hover:text-blue-500">
						<span class="mr-2 h-4 w-4">
							<!-- SVG content remains the same -->
							<svg
								class="h-full w-full"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
								stroke-linecap="round"
								stroke-linejoin="round"
							>
								<!-- Update this in all SVG conditional blocks throughout the component -->
								{#if link.icon === 'map-pin'}
									<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
									<circle cx="12" cy="10" r="3"></circle>
								{:else if link.icon === 'mail'}
									<path
										d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
									></path>
									<polyline points="22,6 12,13 2,6"></polyline>
								{:else if link.icon === 'twitter'}
									<path
										d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"
									></path>
								{:else if link.icon === 'linkedin'}
									<path
										d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
									></path>
									<rect x="2" y="9" width="4" height="12"></rect>
									<circle cx="4" cy="4" r="2"></circle>
								{:else if link.icon === 'github'}
									<path
										d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
									></path>
								{/if}
							</svg>
						</span>
						{link.name}
					</a>
				{/each}
			</div>
		</div>
	{/if}
</section>
