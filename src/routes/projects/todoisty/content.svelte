<h2 class="mb-4 text-2xl font-bold text-gray-800">Todoisty</h2>
<br />

<div class="space-y-6 text-gray-700">
	<h2 class="mb-4 text-xl font-bold text-gray-800">Project Overview</h2>
	<p>
		<b>Todoisty</b> is a full-stack to-do list application that provides a sleek and user-friendly interface.
		It is designed with a focus on enhancing the user experience by offering practical features and an
		intuitive layout. The application allows users to efficiently manage their daily tasks and stay organized
		with minimal effort.
	</p>

	<p><u><a href="https://github.com/nethbotheju/todoisty">GitHub Repository Here</a></u></p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Features</h2>
	<ul class="ml-4 list-disc">
		<li>
			Users can add tasks with descriptions limited to 90 characters. Each task can optionally
			include a due date and a reminder with a specific time.
		</li>
		<li>
			The reminder system ensures users are notified at the scheduled time. If a reminder is set for
			a task, the application will play a notification tone when the time arrives.
		</li>
		<li>
			Task filtering is available to help users focus on what&#39;s important. Users can filter
			tasks by:
		</li>
		<ul class="ml-4 list-disc">
			<li>
				<b>Today</b>: Displays tasks due today.
			</li>
			<li>
				<b>Tomorrow</b>: Displays tasks scheduled for the next day.
			</li>
			<li>
				<b>Upcoming</b>: Shows tasks scheduled for future dates.
			</li>
			<li>
				<b>All Tasks</b>: Lists every task the user has created.
			</li>
		</ul>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Technical Implementation</h2>
	<b>Backend</b>
	<p>
		The backend is developed using <b>Node.js</b> with the <b>Express</b> framework. It provides all
		the necessary RESTful API endpoints required for frontend communication. For data storage, the
		application uses a <b>PostgreSQL</b> database, which ensures reliable and efficient data handling.
	</p>

	<b>Frontend</b>
	<p>
		The frontend is built with <b>Vue.js</b>, offering a modern and reactive user interface. For
		styling,
		<b>Tailwind CSS</b> is used to create a clean, responsive, and visually appealing design. The
		frontend communicates with the backend through <b>REST API</b> calls to fetch and send data seamlessly.
	</p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Future Enhancements</h2>
	<ul class="ml-4 list-disc">
		<li>
			<b>Task Labels and Filtering</b>: Implement a labeling system where users can assign labels to
			tasks. Labels will help categorize tasks and allow users to filter tasks based on specific
			labels.
		</li>
		<li>
			<b>User Authentication System</b>: Introduce a user-based system with secure user registration
			and login functionality, ensuring each user has their personalized task list and settings.
		</li>
		<li>
			<b>Database Migration to MongoDB</b>: Migrate the current PostgreSQL database to MongoDB, and
			host the database on MongoDB Atlas for better scalability and flexibility.
		</li>
		<li>
			<b>Mobile Application</b>: Develop a mobile application to provide users with on-the-go access
			to their tasks, enhancing accessibility and convenience.
		</li>
	</ul>
</div>
