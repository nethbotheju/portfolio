<script>
	// Sample education data - replace with your own
	const educationHistory = [
		{
			logo: '/images/cs50.jpg', // Add your university logos to static/images
			name: 'CS50x Introduction to Computer Science',
			institution: 'CS50',
			issueDate: 'Dec 2023',
			credentialId: '95b371a9-27fc-4326-b98c-6482faacf4d3',
			credentialLink: 'https://cs50.harvard.edu/certificates/95b371a9-27fc-4326-b98c-6482faacf4d3',
			description:
				'Specialized in artificial intelligence and machine learning. Graduated with honors.'
		},
		{
			logo: '/images/esoft.jpg',
			name: 'Certificate in Information Technology',
			institution: 'ESOFT Metro Campus',
			issueDate: 'Oct 2023',
			credentialId: '00147421 / E175054',
			credentialLink: 'https://drive.google.com/file/d/1lqq2JOVmXKpOhReqBI8awhOVOMm2beCI/view',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		},
		{
			logo: '/images/iit.jpg',
			name: 'Foundation Certificate in Higher Education(IT) - Distinction',
			institution: 'Informatics Institute of Technology (IIT Campus)',
			issueDate: 'Sep 2023',
			credentialId: '20221813',
			credentialLink: 'https://drive.google.com/file/d/1nRw0h24neH9_GUMSzJF8ejrLTnt-nFr1/view',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		},
		{
			logo: '/images/esoft.jpg',
			name: 'Diploma in English',
			institution: 'ESOFT Metro Campus',
			issueDate: 'Aug 2023',
			credentialId: '00147421 / E175054',
			credentialLink: 'https://drive.google.com/file/d/1aiwTw3D220Gc_DhAOI82WUqO4ushvIqn/view',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		},
		{
			logo: '/images/msc.png',
			name: 'G.C.E Ordinary Level Exam - 8As (including Mathematics and English) and 1B',
			institution: 'Maris Stella College Negombo',
			issueDate: 'Nov 2023',
			credentialId: '10765271',
			credentialLink: 'https://drive.google.com/file/d/1XVwERocW04E-M9NZXjO1Tur5rEzdoyEJ/view',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		},
		{
			logo: '/images/cambridge.jpg',
			name: 'Cambridge English B1 Preliminary - Level A2',
			institution: 'Cambridge University Press & Assessment English',
			issueDate: 'Nov 2019',
			credentialId: '19ALK0015001',
			credentialLink:
				'https://drive.google.com/file/d/1-Zy-Hnc7wDg1kDLvUKTQp-mD16exJu5r/view?usp=sharing',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		},
		{
			logo: '/images/cambridge.jpg',
			name: 'Cambridge English A2 Key - Pass',
			institution: 'Cambridge University Press & Assessment English',
			issueDate: 'Nov 2018',
			credentialId: '18ALK0010024',
			credentialLink:
				'https://drive.google.com/file/d/1yWAlz1sZ8JVZ71jqhNEOZ-kPH1I61-mt/view?usp=sharing',
			description:
				"Focus on software development and systems architecture. Dean's list all semesters."
		}
	];
</script>

<div class="education-container">
	<!-- Education Items -->
	<div class="space-y-12">
		{#each educationHistory as education, index}
			<div class="education-item">
				<!-- Logo and Period -->
				<div class="item-meta">
					<div class="logo-container">
						<img src={education.logo} alt={education.institution} class="logo-image" />
					</div>
				</div>

				<!-- Content -->
				<div class="item-content">
					<div class="p-2">
						<h3 class="text-xl font-bold text-gray-800">{education.name}</h3>
						<h4 class="text-md mt-1 font-semibold text-gray-600">{education.institution}</h4>
						<h4 class="text-md mt-1 font-semibold text-gray-600">Issued {education.issueDate}</h4>
						<h4 class="text-md mt-1 font-semibold text-gray-600">
							Credential ID {education.credentialId}
						</h4>
						<h4 class="text-md mt-1 font-semibold text-gray-600 hover:text-gray-500">
							<a href={education.credentialLink}>Show Credential</a>
						</h4>
					</div>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.education-container {
		position: relative;
		padding-left: 20px;
	}

	.education-item {
		position: relative;
		display: flex;
		flex-direction: column;
	}

	.item-meta {
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

	.item-content {
		width: 100%;
	}

	/* Media Queries for Responsive Design */
	@media (min-width: 688px) {
		.education-container {
			padding-left: 2px;
		}

		.education-item {
			flex-direction: row;
		}

		.item-meta {
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
	}
</style>
