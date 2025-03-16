<script>
	// Import necessary components
	import Profile from '../../../components/profile.svelte';
	import Footer from '../../../components/footer.svelte';
	import Navbar from '../../../components/navbar.svelte';

	import Content from './content.svelte';
</script>

<svelte:head>
	<title>Portfolio | Projects | Neth Botheju</title>
</svelte:head>

<div class="min-h-screen bg-white">
	<Navbar />
	<main class="container mx-auto max-w-4xl px-4 py-8">
		<div class="flex flex-col gap-12 lg:flex-row">
			<div class="w-full lg:w-1/5">
				<Profile />
			</div>
			<div class="w-full lg:w-4/5">
				<Content />
			</div>
		</div>
	</main>
	<Footer />
</div>
