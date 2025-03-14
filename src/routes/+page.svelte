<!-- App.svelte -->
<script>
	// Import necessary components
	import Profile from '../components/profile.svelte';
	import About from '../components/about.svelte';
	import Footer from '../components/footer.svelte';
	import Navbar from '../components/navbar.svelte';
</script>

<svelte:head>
	<title>Neth Botheju</title>
	<link rel="icon" href="/favicon.ico" sizes="any" />
	<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" />
	<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png" />
	<link rel="apple-touch-icon" href="/apple-touch-icon.png" />
	<meta name="theme-color" content="#ffffff" />
</svelte:head>

<div class="min-h-screen bg-white">
	<Navbar />
	<main class="container mx-auto max-w-4xl px-4 py-8">
		<div class="flex flex-col gap-10 lg:flex-row">
			<div class="w-full lg:w-1/5">
				<Profile />
			</div>
			<div class="w-full lg:w-4/5">
				<About />
			</div>
		</div>
	</main>
	<Footer />
</div>
