<script>
	import Profile from '../../components/profile.svelte';
	import Footer from '../../components/footer.svelte';
	import Navbar from '../../components/navbar.svelte';

	import Education from './education.svelte';
	import Certifications from './certifications.svelte';
</script>

<svelte:head>
	<title>Education | Neth Botheju</title>
</svelte:head>

<div class="min-h-screen bg-white">
	<Navbar />
	<main class="container mx-auto max-w-4xl px-4 py-8">
		<div class="flex flex-col gap-10 lg:flex-row">
			<div class="w-full lg:w-1/5">
				<Profile />
			</div>
			<div class="w-full lg:w-4/5">
				<h1 class="mb-8 text-3xl font-bold text-gray-800">Education</h1>
				<Education />

				<h1 class="mt-12 mb-8 text-3xl font-bold text-gray-800">Certifications</h1>
				<Certifications />
			</div>
		</div>
	</main>
	<Footer />
</div>
