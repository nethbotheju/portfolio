<h2 class="mb-4 text-2xl font-bold text-gray-800">Git cli client (gity)</h2>
<br />

<div class="space-y-6 text-gray-700">
	<h2 class="mb-4 text-xl font-bold text-gray-800">Project Overview</h2>
	<p>
		<b>Gity</b> is a lightweight command-line interface (CLI) tool built with Rust that streamlines common
		Git operations. The goal is to create a user-friendly CLI Git client that combines common Git commands
		with additional integrated features.
	</p>

	<p><u><a href="https://github.com/nethbotheju/gity">GitHub Repository Here</a></u></p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Features</h2>

	<p>
		Gity works with officially initialized Git repositories or existing projects. Feel free to
		switch between Gity and Git at any time without issue.
	</p>

	<ul class="ml-4 list-disc">
		<li>Near-instant execution (thanks to Rust's zero-cost abstractions)</li>
		<li>Common Git commands:</li>
		<ul class="ml-4 list-disc">
			<li>
				<code>gity init .</code> - Initializes a project by creating a <code>.git</code> folder
			</li>
			<li>
				<code>gity add .</code> - Stages changes
			</li>
			<li>
				<code>git commit -m "&lt;message&gt;"</code> - Commits staged changes with a message
			</li>
			<li>
				<code>gity push</code> - Pushes commits to the remote repository
			</li>
		</ul>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Technical Implementation</h2>
	<ul class="ml-4 list-disc">
		<li>
			<b>Language</b>: Rust — a modern, fast, and memory-safe language that executes with
			near-instant speed.
		</li>
		<li>
			<b>Package Manager</b>: Cargo — Rust&#39;s package manager for easy dependency management and
			building.
		</li>
		<li><b>Libraries</b>:</li>
		<ul class="ml-4 list-disc">
			<li>
				<b><u><a href="https://github.com/clap-rs/clap">clap</a></u></b> - Functional components with
				hooks for state management
			</li>
			<li>
				<b><u><a href="https://github.com/rust-lang/git2-rs">git2-rs</a></u></b> - Open-source Rust bindings
				for interacting with Git repositories
			</li>
		</ul>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Releases</h2>
	<h3 class="mb-4 text-lg font-bold text-gray-800">v0.1.0 (Latest)</h3>
	<p>
		Gity currently supports a limited set of Git operations, with more features planned for future
		releases. The primary focus in this version is to implement the simplest Git commands.
	</p>

	<b>Supported Commands</b>
	<ul class="ml-4 list-disc">
		<li><code>gity init .</code> — Initializes a new Git repository in the current directory.</li>
		<li>
			<code>gity add .</code> — Tracks newly added files in the repository (note: only newly added files
			are tracked; deleted files are not).
		</li>
		<li>
			<code>gity commit -m "&lt;message&gt;"</code> — Commits changes with a short message (only supports
			a commit title, not a detailed description).
		</li>
		<li><code>gity push</code> — Pushes local commits to the remote repository.</li>
	</ul>

	<b>Known Limitations</b>
	<ul class="ml-4 list-disc">
		<li>
			<code>gity add .</code> only tracks newly added files. Deleted or modified files are not currently
			handled.
		</li>
		<li>
			<code>gity commit -m "&lt;message&gt;"</code> only accepts a short commit title; it does not yet
			support detailed commit descriptions.
		</li>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Future Enhancements</h2>
	<ul class="ml-4 list-disc">
		<li>Implement advanced Git commands (e.g., branch management, merge, rebase)</li>
		<li>Add AI-based auto-commit message generation integrated with the CLI</li>
		<li>Introduce combined commands for easier and faster workflows</li>
	</ul>
</div>
