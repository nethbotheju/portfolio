<script>
	import Profile from '../../components/profile.svelte';
	import Footer from '../../components/footer.svelte';
	import Navbar from '../../components/navbar.svelte';
</script>

<div class="min-h-screen bg-white">
	<Navbar />
	<main class="container mx-auto max-w-4xl px-4 py-8">
		<div class="flex flex-col gap-10 lg:flex-row">
			<div class="w-full lg:w-1/5">
				<Profile />
			</div>
			<div class="w-full lg:w-4/5">
				<div class="mb-4">
					<h2 class="mb-2 text-2xl font-bold text-gray-800">Resume</h2>
					<div class="flex justify-end">
						<a
							href="https://raw.githubusercontent.com/nethbotheju/portfolio/main/static/cv.pdf"
							download="resume.pdf"
							target="_blank"
							rel="noopener noreferrer"
							class="rounded bg-blue-500 px-4 py-2 text-white transition-colors hover:bg-blue-600"
						>
							Download CV
						</a>
					</div>
				</div>

				<div class="pdf-container mb-8 w-full overflow-hidden rounded border border-gray-300">
					<iframe
						src="https://mozilla.github.io/pdf.js/web/viewer.html?file=https://raw.githubusercontent.com/nethbotheju/portfolio/main/static/cv.pdf#toolbar=0"
						class="h-full w-full"
						title="cv-preview"
					>
					</iframe>
				</div>
			</div>
		</div>
	</main>
	<Footer />
</div>

<style>
	.pdf-container {
		aspect-ratio: 8.5/11;
		height: 85vh; /* Increased from 70vh to 85vh */
	}

	@media screen and (max-width: 768px) {
		.pdf-container {
			height: 70vh; /* Increased from 60vh */
		}
	}

	@media screen and (max-width: 480px) {
		.pdf-container {
			height: 60vh; /* Increased from 50vh */
		}
	}
</style>
