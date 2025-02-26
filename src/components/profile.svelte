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
	<!-- Desktop View (> 925px) -->
	<div class="mb-6 hidden items-start md:flex-row lg:block">
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
				software development, backend technologies, AI, and machine learning. Skilled in Python,
				Java, C, and C#. Driven by innovation and problem-solving.
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
								{#if link.icon === 'map-pin'}
									<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
									<circle cx="12" cy="10" r="3"></circle>
								{:else if link.icon === 'mail'}
									<path
										d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
									></path>
									<polyline points="22,6 12,13 2,6"></polyline>
								{:else if link.icon === 'book'}
									<path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path>
									<path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>
								{:else if link.icon === 'twitter'}
									<path
										d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"
									></path>
								{:else if link.icon === 'linkedin'}
									<path
										d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
									></path>
									<rect x="2" y="9" width="4" height="12"></rect>
									<circle cx="4" cy="4" r="2"></circle>
								{:else if link.icon === 'instagram'}
									<rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
									<path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
									<line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
								{:else if link.icon === 'github'}
									<path
										d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
									></path>
								{:else if link.icon === 'book-open'}
									<path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path>
									<path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path>
								{/if}
							</svg>
						</span>
						{link.name}
					</a>
				{/each}
			</div>
		</div>
	</div>

	<!-- Mobile View (< 925px) -->
	<div class="flex items-center justify-between lg:hidden">
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

	<!-- Mobile Social Links Dropdown -->
	{#if showSocialLinks}
		<div class="mt-4 rounded-md bg-gray-50 p-4 shadow-md lg:hidden">
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
								{#if link.icon === 'map-pin'}
									<path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
									<circle cx="12" cy="10" r="3"></circle>
								{:else if link.icon === 'mail'}
									<path
										d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
									></path>
									<polyline points="22,6 12,13 2,6"></polyline>
								{:else if link.icon === 'book'}
									<path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path>
									<path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path>
								{:else if link.icon === 'twitter'}
									<path
										d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"
									></path>
								{:else if link.icon === 'linkedin'}
									<path
										d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"
									></path>
									<rect x="2" y="9" width="4" height="12"></rect>
									<circle cx="4" cy="4" r="2"></circle>
								{:else if link.icon === 'instagram'}
									<rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
									<path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
									<line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
								{:else if link.icon === 'github'}
									<path
										d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"
									></path>
								{:else if link.icon === 'book-open'}
									<path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"></path>
									<path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"></path>
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
