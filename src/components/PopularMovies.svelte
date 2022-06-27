<script lang="ts">
	type Movie = {
		id: String;
		title: String;
		poster_path: String;
	};
	export let popularMovies: Movie[];
</script>

<ul>
	{#each popularMovies as movie}
		<li>
			<p>{movie.id}</p>
			<p>{movie.title}</p>
			<a href={'/movie/' + movie.id}>
				<img src={'https://image.tmdb.org/t/p/w500/' + movie.poster_path} alt={movie.title} />
			</a>
		</li>
	{/each}
</ul>
