<script>
	import Page from '../+page.svelte';
</script>

<h2 class="mb-4 text-2xl font-bold text-gray-800">Realtime Ticketing System</h2>
<br />

<div class="space-y-6 text-gray-700">
	<h2 class="mb-4 text-xl font-bold text-gray-800">Project Overview</h2>
	<p>
		<b>Realtime Ticketing System</b> is an automated ticketing system with both client and server
		sides. This project was developed as an assessment for the <b>OOP module</b> in the second year,
		demonstrating Java OOP concepts throughout the system.
	</p>
	<p>
		The project includes two client applications: a web client and a CLI client, both synchronized
		with a single server. The application operates with a single user, meaning both clients are
		always in sync. The system simulates vendors and customers. Users can configure the number of
		vendors and customers, ticket releasing and retrieving rates, and the maximum ticket count.
		Based on these settings, the application runs and demonstrates its performance, particularly
		focusing on concurrency.
	</p>

	<p>
		<u
			><a href="https://github.com/nethbotheju/RealtimeTicketingSystem">GitHub Repository Here</a
			></u
		>
	</p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Features</h2>
	<ul class="ml-4 list-disc">
		<li>In the web client, you can view the number of available tickets with real-time updates.</li>
		<li>The web client includes a control panel to start, reset, and stop the program.</li>
		<li>You can view a sales bar chart for each day in the web client.</li>
		<li>
			The web client also allows you to stop or add new vendors or customers dynamically while the
			program is running.
		</li>
		<li>Both the CLI client and web client display a real-time logger.</li>
		<li>
			Customers can be assigned a priority, giving them precedence when retrieving tickets from the
			ticket pool.
		</li>
		<li>If the program is stopped and restarted, it will resume from where it left off.</li>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Technical Implementation</h2>
	<b>Backend</b>
	<p>
		The backend of the application is developed using <b></b> and <b>Spring Boot</b>. It contains
		the core logic of the system, handling all the main operations such as ticket releasing,
		retrieving, and managing vendors and customers. The necessary configuration data required to run
		the application is stored in a <code>config.json</code> file, while the sales data is
		persistently stored in an <b>SQLite</b>
		database. The backend seamlessly interacts with the database to maintain and update sales records.
	</p>

	<b>Frontend (Web Client)</b>
	<p>
		The frontend web client is built with <b>Angular</b> and <b>Tailwind CSS</b>, providing a modern
		and responsive user interface. It communicates with the backend through <b>REST APIs</b>
		for general operations and uses <b>WebSockets</b>, specifically implemented with
		<b>Stomp.js</b>, for real-time updates. This allows the web client to display live data such as
		available tickets and sales statistics without needing to refresh the page manually.
	</p>

	<b>CLI Client</b>
	<p>
		The CLI client is developed purely in <b>Java</b> and connects to the backend via
		<b>REST APIs</b>
		for standard data requests. It also establishes a java <b>socket</b> connection to receive real-time
		updates, similar to the web client. The CLI client offers an alternative interface for interacting
		with the system, displaying logs and live data directly in the terminal.
	</p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Future Enhancements</h2>
	<ul class="ml-4 list-disc">
		<li>Redesign the UI to make it fully responsive for all devices.</li>
		<li>
			Convert the CLI application into an executable file with improved user interaction, commands,
			and instructions.
		</li>
	</ul>
</div>
