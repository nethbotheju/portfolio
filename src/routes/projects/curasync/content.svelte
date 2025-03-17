<h2 class="mb-4 text-2xl font-bold text-gray-800">CuraSync</h2>
<br />

<div class="space-y-6 text-gray-700">
	<h2 class="mb-4 text-xl font-bold text-gray-800">Project Overview</h2>
	<p>
		<b>Curasync</b> is a collaborative group project developed as part of the second-year Software Development
		Group Project (SDGP) module. It is a comprehensive digital healthcare solution designed to seamlessly
		connect doctors, patients, pharmacies, and laboratories within a unified platform. Curasync aims
		to streamline communication between healthcare stakeholders, enhance the management of medical records,
		and simplify the sharing of prescriptions and laboratory reports. Our platform ensures a more efficient,
		secure, and connected healthcare experience for both patients and healthcare providers.
	</p>

	<p>
		Our team consisted of five members, and I primarily contributed to the <b>backend development</b
		>
		and the <b>visualization feature</b> implementation.
	</p>

	<p><u><a href="https://github.com/CuraSync">GitHub Repository Here</a></u></p>

	<p><u><a href="https://curasync.vercel.app">Landing page Here</a></u></p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Features</h2>

	<ul class="ml-4 list-disc">
		<li>
			<b>Secure Communication</b><br /> Curasync facilitates secure, real-time communication between
			the different roles within the healthcare ecosystem.
		</li>
		<li>
			<b>Interactive Medical History Timeline</b><br /> We developed a unique timeline feature that visually
			presents a patient&#39;s complete medical history in a clear, chronological format. Both doctors
			and patients can access and interact with this timeline to view previous consultations, prescriptions,
			lab reports, and other critical health data. This promotes better decision-making and continuity
			of care.
		</li>
		<li>
			<b>Report Visualization and Explanation</b><br /> Laboratory reports are often filled with
			complex medical terminology and data that can be difficult for patients to interpret. Our
			Visualization Feature addresses this by extracting and analyzing lab report data and providing
			simplified explanations.
			<ul class="ml-4 list-disc">
				<li>
					The goal is not to predict or offer medical advice, but to explain the contents of the
					report in a way patients can easily understand.
				</li>
				<li>
					This enhances health literacy and empowers patients to take an active role in managing
					their health.
				</li>
			</ul>
		</li>
		<li>
			<b>Secure Development and Data Protection</b><br />
			Since we handle highly sensitive personal health information (PHI), we prioritized data security
			throughout the development process.
			<ul class="ml-4 list-disc">
				<li>All patient data is fully encrypted during transmission and storage.</li>
				<li>
					We implemented robust authentication and authorization mechanisms to ensure data access is
					restricted to authorized users only.
				</li>
				<li>
					Our system adheres to best practices in secure software development to maintain
					confidentiality, integrity, and availability.
				</li>
			</ul>
		</li>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Technical Implementation</h2>
	<b>Backend</b>
	<p>
		The backend of Curasync is built with Node.js and Express.js, providing a robust and scalable
		API. We use MongoDB Atlas to store structured medical data, while Cloudinary handles static file
		storage for documents like prescriptions and lab reports.
	</p>
	<p>
		To ensure data security, sensitive information is encrypted using AES-256, protecting patient
		records at rest. Authentication and authorization are managed with JWT, incorporating both
		access and refresh tokens.
	</p>
	<p>
		Redis is used to store and manage refresh tokens efficiently, enabling secure session
		management. The backend services are deployed and hosted on Render.com, which offers scalable
		infrastructure and continuous deployment for seamless operations.
	</p>

	<b>Visualization Feature</b>
	<p>
		The visualization feature, developed in Python, simplifies lab reports for patients. Using
		Pytesseract (an OCR tool), we extract data from scanned lab reports. This data is then processed
		by a custom algorithm that filters and structures the information.
	</p>
	<p>
		Finally, we integrate Google Gemini (Free Tier) to generate simplified, patient-friendly
		explanations of the reports. The goal is not to offer medical advice but to make complex medical
		information easier for patients to understand.
	</p>
</div>
