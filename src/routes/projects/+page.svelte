<script>
	// Import necessary components
	import Profile from '../../components/profile.svelte';
	import Footer from '../../components/footer.svelte';
	import Navbar from '../../components/navbar.svelte';
	import { writable } from 'svelte/store';

	// Search functionality
	let searchQuery = '';

	let filterType = 'all';

	// Sample project data remains the same
	const projects = [
		{
			id: 1,
			title: 'Gity',
			description: 'Gity is a lightweight command-line interface (CLI) tool built with Rust.',
			languages: [{ name: 'Rust', logo: '/images/tech/rust.svg' }],
			type: 'individual',
			link: '/projects/gity'
		},
		{
			id: 2,
			title: 'Curasync',
			description: 'Curasync is an all-in-one digital medical solution.',
			languages: [
				{ name: 'Nextjs.js', logo: '/images/tech/nextjs.svg' },
				{ name: 'Node.js', logo: '/images/tech/nodejs.svg' },
				{ name: 'Tailwind', logo: '/images/tech/tailwind.svg' }
			],
			type: 'collaborative',
			link: '/projects/curasync'
		},
		{
			id: 3,
			title: 'Movie Prediction',
			description:
				"Movie Prediction Application that predicts the movie based on the user's summary.",
			languages: [
				{ name: 'Vue.js', logo: '/images/tech/vue.svg' },
				{ name: 'Python', logo: '/images/tech/python.svg' },
				{ name: 'Flask', logo: '/images/tech/flask.svg' }
			],
			type: 'individual',
			link: '/projects/movie-prediction'
		},
		{
			id: 4,
			title: 'Todoisty',
			description: 'Todoisty is a full-stack user-friendly to-do list application.',
			languages: [
				{ name: 'Vue.js', logo: '/images/tech/vue.svg' },
				{ name: 'Node.js', logo: '/images/tech/nodejs.svg' },
				{ name: 'Tailwind', logo: '/images/tech/tailwind.svg' }
			],
			type: 'individual',
			link: '/projects/todoisty'
		},
		{
			id: 5,
			title: 'Real time Ticketing System',
			description: 'An automated ticketing system with both clients and server side.',
			languages: [
				{ name: 'Springboot', logo: '/images/tech/springboot.svg' },
				{ name: 'Angular', logo: '/images/tech/angular.svg' },
				{ name: 'Tailwind', logo: '/images/tech/tailwind.svg' }
			],
			type: 'individual',
			link: '/projects/real-time-ticketing-system'
		},
		{
			id: 6,
			title: 'Portfolio',
			description: 'Portfolio which I developed with Svelte.',
			languages: [
				{ name: ' Svelte', logo: '/images/tech/svelte.svg' },
				{ name: 'Tailwind', logo: '/images/tech/tailwind.svg' }
			],
			type: 'individual',
			link: '/projects/portfolio'
		}
	];

	// Filter projects based on search query and filter type
	$: filteredProjects = projects.filter((project) => {
		// First, check the filter type
		if (filterType !== 'all' && project.type !== filterType) return false;

		// Then apply search query if present
		if (!searchQuery) return true;

		const query = searchQuery.toLowerCase();

		// Search in title
		if (project.title.toLowerCase().includes(query)) return true;

		// Search in description
		if (project.description.toLowerCase().includes(query)) return true;

		// Search in languages
		if (project.languages.some((lang) => lang.name.toLowerCase().includes(query))) return true;

		return false;
	});
</script>

<svelte:head>
	<title>Projects | Neth Botheju</title>
</svelte:head>

<div class="min-h-screen bg-white">
	<Navbar />
	<main class="container mx-auto max-w-4xl px-4 py-8">
		<div class="flex flex-col gap-10 lg:flex-row">
			<div class="w-full lg:w-1/5">
				<Profile />
			</div>
			<div class="w-full lg:w-4/5">
				<div class="search-filter-container mb-6">
					<div class="filter-options mb-4">
						<button
							class={`filter-button ${filterType === 'all' ? 'active' : ''}`}
							on:click={() => (filterType = 'all')}
						>
							All
						</button>
						<button
							class={`filter-button ${filterType === 'individual' ? 'active' : ''}`}
							on:click={() => (filterType = 'individual')}
						>
							Individual
						</button>
						<button
							class={`filter-button ${filterType === 'collaborative' ? 'active' : ''}`}
							on:click={() => (filterType = 'collaborative')}
						>
							Collaborative
						</button>
					</div>
					<div class="relative">
						<input
							type="text"
							placeholder="Search projects..."
							bind:value={searchQuery}
							class="search-input"
						/>
						<svg
							class="absolute top-1/2 right-3 h-5 w-5 -translate-y-1/2 text-gray-400"
							xmlns="http://www.w3.org/2000/svg"
							viewBox="0 0 20 20"
							fill="currentColor"
							aria-hidden="true"
						>
							<path
								fill-rule="evenodd"
								d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
								clip-rule="evenodd"
							/>
						</svg>
					</div>
				</div>

				<div class="project-container">
					{#if filteredProjects.length === 0}
						<div class="empty-state">
							<p>No projects match your search criteria.</p>
						</div>
					{:else}
						{#each filteredProjects as project}
							<article class="project-card">
								<div class="project-type-badge {project.type}">
									{project.type}
								</div>
								<a href={project.link} class="project-title">
									<h2>{project.title}</h2>
								</a>
								<p class="description">{project.description}</p>

								<div class="languages">
									{#each project.languages as lang}
										<div class="language">
											<img src={lang.logo} alt={lang.name} />
											<span>{lang.name}</span>
										</div>
									{/each}
								</div>
							</article>
						{/each}
					{/if}
				</div>
			</div>
		</div>
	</main>
	<Footer />
</div>

<style>
	.search-container {
		width: 100%;
	}

	.search-input {
		width: 100%;
		padding: 0.75rem 2.5rem 0.75rem 1rem;
		border: 2px solid #e5e7eb;
		border-radius: 8px;
		font-size: 1rem;
		color: #333;
		background-color: white;
		transition:
			border-color 0.2s ease,
			box-shadow 0.2s ease;
	}

	.search-input:focus {
		outline: none;
		border-color: #3b82f6;
		box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
	}

	.empty-state {
		text-align: center;
		padding: 2.5rem;
		color: #6b7280;
		background: #f9fafb;
		border-radius: 8px;
		border: 1px dashed #e5e7eb;
	}

	.project-container {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
		max-height: 75vh; /* Set maximum height for scrolling */
		overflow-y: auto; /* Enable vertical scrolling */
		padding-right: 0.5rem; /* Space for scrollbar */
	}

	/* Custom scrollbar styling */
	.project-container::-webkit-scrollbar {
		width: 6px;
	}

	.project-container::-webkit-scrollbar-track {
		background: #f1f1f1;
		border-radius: 10px;
	}

	.project-container::-webkit-scrollbar-thumb {
		background: #c1c1c1;
		border-radius: 10px;
	}

	.project-container::-webkit-scrollbar-thumb:hover {
		background: #a8a8a8;
	}

	.project-card {
		background: white;
		border-radius: 8px;
		padding: 1.25rem; /* Reduced padding */
		box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1); /* More subtle, spread-out shadow */
		transition:
			transform 0.3s ease,
			box-shadow 0.3s ease;
		display: flex;
		flex-direction: column;
		min-height: 180px; /* Reduced height from 230px */
		width: 100%;
		position: relative;
	}

	.project-card:hover {
		transform: translateY(-3px); /* Smaller lift on hover */
		box-shadow: 0 8px 15px rgba(0, 0, 0, 0.12); /* Slightly darker shadow on hover */
	}

	.project-title {
		text-decoration: none;
		color: #2a2a2a;
		transition: color 0.2s ease;
	}

	.project-title:hover {
		color: #3b82f6;
		text-decoration: underline;
	}

	.project-card h2 {
		margin-top: 0;
		font-size: 1.5rem;
	}

	.description {
		flex-grow: 1;
		color: #555;
		line-height: 1.6;
	}

	.languages {
		display: flex;
		flex-wrap: wrap;
		gap: 0.5rem; /* Reduced gap */
		margin: 1rem 0; /* Reduced margin */
	}

	.language {
		display: flex;
		align-items: center;
		gap: 0.25rem;
		background: #f5f5f5;
		padding: 0.2rem 0.6rem; /* Slightly smaller padding */
		border-radius: 20px; /* Slightly smaller radius */
		font-size: 0.8rem; /* Slightly smaller font */
	}

	.language img {
		width: 16px; /* Smaller icon */
		height: 16px;
	}

	.project-type-badge {
		position: absolute;
		top: 1rem;
		right: 1rem;
		padding: 0.25rem 0.75rem;
		border-radius: 20px;
		font-size: 0.75rem;
		text-transform: capitalize;
	}

	.project-type-badge.individual {
		background: #e1f5fe;
		color: #0277bd;
	}

	.project-type-badge.collaborative {
		background: #e8f5e9;
		color: #2e7d32;
	}

	.search-filter-container {
		width: 100%;
	}

	.filter-options {
		display: flex;
		gap: 0.75rem;
		margin-bottom: 1rem;
	}

	.filter-button {
		padding: 0.5rem 1rem;
		border-radius: 20px;
		background: #f5f5f5;
		border: none;
		font-size: 0.875rem;
		cursor: pointer;
		transition: all 0.2s ease;
	}

	.filter-button:hover {
		background: #e5e5e5;
	}

	.filter-button.active {
		background: #3b82f6;
		color: white;
	}

	/* Responsive adjustments */
	@media (max-width: 768px) {
		.project-container {
			max-height: 60vh;
		}

		.project-type-badge {
			/* Smaller badge on mobile */
			padding: 0.2rem 0.5rem;
			font-size: 0.7rem;
		}
	}

	/* Update responsive adjustment for smaller tiles */
	@media (max-width: 480px) {
		.project-container {
			max-height: 70vh;
		}

		.project-card {
			min-height: 200px; /* Adjusted for mobile */
		}

		.project-card {
			min-height: 200px; /* Adjusted for mobile */
			padding-top: 2.5rem; /* Add space at top for the badge */
		}
	}
</style>
