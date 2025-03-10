<script>
	// Sample education data - replace with your own
	const educationHistory = [
		{
			logo: '/images/uow.png', // Add your university logos to static/images
			institution: 'University of Westminster',
			degree: 'BSc (Hones) Computer Science',
			period: '2023 - 2026',
			description:
				'Specialized in artificial intelligence and machine learning. Graduated with honors.'
		},
		{
			logo: '/images/msc.png',
			institution: 'Maris Stella College Negombo',
			degree: 'Secoundary Education',
			period: '2011 - 2022',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		}
	];
</script>

<div class="education-timeline relative ml-4">
	<!-- Timeline Line - visible on all screen sizes -->
	<div class="timeline-line"></div>

	<!-- Timeline Items -->
	<div class="space-y-12">
		{#each educationHistory as education, index}
			<div class="timeline-item">
				<!-- Timeline Dot -->
				<div class="timeline-dot"></div>

				<!-- Logo and Period -->
				<div class="timeline-meta">
					<div class="logo-container">
						<img src={education.logo} alt={education.institution} class="logo-image" />
					</div>
					<div class="period-container">
						<span class="period">{education.period}</span>
					</div>
				</div>

				<!-- Content -->
				<div class="timeline-content">
					<div class="p-2">
						<h3 class="text-xl font-bold text-gray-800">{education.institution}</h3>
						<h4 class="text-md mt-1 font-semibold text-gray-600">{education.degree}</h4>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.education-timeline {
		position: relative;
		padding-left: 20px;
	}

	.timeline-line {
		position: absolute;
		left: 0;
		top: 0;
		bottom: 0;
		width: 2px;
		background: linear-gradient(to bottom, #3b82f6, #60a5fa);
		border-radius: 999px;
	}

	.timeline-item {
		position: relative;
		display: flex;
		flex-direction: column;
	}

	.timeline-dot {
		position: absolute;
		left: -25px;
		top: 24px;
		width: 16px;
		height: 16px;
		background-color: #3b82f6;
		border-radius: 50%;
		border: 4px solid white;
		box-shadow: 0 0 0 2px #93c5fd;
		z-index: 1;
	}

	.timeline-meta {
		display: flex;
		align-items: center;
		margin-bottom: 0.75rem;
	}

	.logo-container {
		width: 52px;
		height: 52px;
		border-radius: 50%;
		overflow: hidden;
		display: flex;
		align-items: center;
		justify-content: center;
		background-color: #f3f4f6;
		box-shadow:
			0 4px 6px -1px rgba(0, 0, 0, 0.1),
			0 2px 4px -1px rgba(0, 0, 0, 0.06);
		margin-right: 1rem;
	}

	.logo-image {
		width: 40px;
		height: 40px;
		object-fit: contain;
	}

	.period {
		font-size: 0.875rem;
		font-weight: 600;
		color: #2563eb;
	}

	.timeline-content {
		width: 100%;
	}

	/* Media Queries for Responsive Design */
	@media (min-width: 688px) {
		.education-timeline {
			padding-left: 2px;
		}

		.timeline-item {
			flex-direction: row;
		}

		.timeline-meta {
			width: 25%;
			flex-direction: column;
			align-items: flex-end;
			padding-right: 2rem;
			margin-bottom: 0;
		}

		.logo-container {
			width: 64px;
			height: 64px;
			margin-right: 0;
			margin-bottom: 0.75rem;
		}

		.logo-image {
			width: 48px;
			height: 48px;
		}

		.timeline-dot {
			left: -9px;
		}
	}
</style>
