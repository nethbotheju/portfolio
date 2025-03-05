<!-- components/Navbar.svelte -->
<script>
	let menuOpen = false;

	function toggleMenu() {
		menuOpen = !menuOpen;
	}

	const navItems = [
		{ name: 'Projects', href: '/projects' },
		// { name: 'Publications', href: '/publications' },
		{ name: 'Qualifications', href: '/qualifications' },
		{ name: 'Resume', href: '/resume' }
	];
</script>

<header class="bg-white py-4 shadow-sm">
	<div
		class="container mx-auto flex max-w-4xl flex-col px-4 md:flex-row md:items-center md:justify-between"
	>
		<div class="flex items-center justify-between">
			<a href="/" class="text-xl font-bold text-gray-800">Neth Pehesara Botheju</a>
			<button
				class="focus:shadow-outline rounded-lg focus:outline-none md:hidden"
				on:click={toggleMenu}
			>
				<svg fill="currentColor" viewBox="0 0 20 20" class="h-6 w-6">
					{#if menuOpen}
						<path
							fill-rule="evenodd"
							d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
							clip-rule="evenodd"
						></path>
					{:else}
						<path
							fill-rule="evenodd"
							d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM9 15a1 1 0 011-1h6a1 1 0 110 2h-6a1 1 0 01-1-1z"
							clip-rule="evenodd"
						></path>
					{/if}
				</svg>
			</button>
		</div>
		<nav
			class={`flex-col md:flex md:flex-row md:items-center ${menuOpen ? 'flex' : 'hidden'} mt-2 md:mt-0`}
		>
			{#each navItems as item}
				<a href={item.href} class="px-2 py-1 text-gray-600 hover:text-blue-500 md:mx-2"
					>{item.name}</a
				>
			{/each}
		</nav>
	</div>
</header>
