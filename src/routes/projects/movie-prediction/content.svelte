<h2 class="mb-4 text-2xl font-bold text-gray-800">Movie Prediction Application</h2>
<br />

<div class="space-y-6 text-gray-700">
	<h2 class="mb-4 text-xl font-bold text-gray-800">Project Overview</h2>
	<p>
		<b>Movie Prediction Application</b> that predicts the movie based on the user's summary or what they
		remember about the movie. The goal is to create an accurate predictor.
	</p>

	<p><u><a href="https://github.com/nethbotheju/movie-prediction">GitHub Repository Here</a></u></p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Features</h2>

	<ul class="ml-4 list-disc">
		<li>
			Users can submit a summary through the frontend web application and receive predictions in a
			user-friendly interface without needing to work with the CLI.
		</li>
		<li>
			Users will receive the top 3 predicted movies based on the submitted summary, along with a
			similarity score for each movie.
		</li>
		<li>
			The frontend will display additional metadata about each predicted movie, such as the release
			year, genres, etc., for better clarification.
		</li>
	</ul>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Technical Implementation</h2>
	<b>Dataset</b>
	<p class="mb-1">
		I couldn't find a dataset on the internet that includes movie data along with the plot as a
		column for each record. So, I merged multiple datasets to create the final dataset.
	</p>
	<ul class="ml-4 list-disc">
		<li>
			First, I obtained three datasets: the IMDb movie dataset, the Wikipedia movie dataset, and a
			dataset containing movie plots with Wikipedia movie IDs.
		</li>
		<li>
			I first merged the IMDb and Wikipedia datasets using the movie name and release year. Then, I
			merged the resulting dataset with the Wikipedia movie plot dataset using the Wikipedia movie
			ID.
		</li>
	</ul>

	<b>Model</b>
	<ul class="ml-4 list-disc">
		<li>
			During model training, after text cleaning, I generated embeddings using the <b
				>all-MiniLM-L6-V2</b
			> model.
		</li>
		<li>
			I fine-tuned the model using triplet loss (anchor = summary text, positive = correct title,
			negative = random title).
		</li>
		<li>I built a FAISS index with the embeddings and saved it for future predictions.</li>
	</ul>

	<b>Backend</b>
	<p>
		The backend of the application has been developed using Python and the Flask framework. It is
		responsible for predicting movies by utilizing a pre-saved FAISS index to perform efficient
		similarity searches. The application exposes APIs to handle both input requests and output
		responses, enabling seamless interaction between the client and the server.
	</p>

	<b>Frontend</b>
	<p>
		The frontend of the application is developed using Vue.js, providing a responsive and
		interactive user interface. It communicates with the backend by connecting to the exposed API
		endpoints, allowing users to send their prompts and receive movie predictions in real time.
	</p>

	<h2 class="mb-4 text-xl font-bold text-gray-800">Future Enhancements</h2>
	<ul class="ml-4 list-disc">
		<li>
			Collect additional information from the user if they know it (e.g., actors, genre, year),
			which can help make more accurate predictions.
		</li>
		<li>
			According to testing, the model seems to overfit and doesn't fully understand the sentences.
			Future work will focus on generalizing the model.
		</li>
		<li>Display movie posters alongside the predicted movies for a better user experience.</li>
	</ul>
</div>
