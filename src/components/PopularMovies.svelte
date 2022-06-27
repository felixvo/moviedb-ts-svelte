<script lang="ts">
	import type { Movie } from 'src/apis/movie';

	export let popularMovies: Movie[];
</script>

<ul class="movie-container">
	{#each popularMovies as movie}
		<li class="movie-item">
			<a href={'/movie/' + movie.id}>
				<img
					class="movie-image"
					src={'https://image.tmdb.org/t/p/w500/' + movie.poster_path}
					alt={movie.title}
				/>
			</a>
			<div>{movie.title}</div>
			<div>{movie.popularity}</div>
			<div>{movie.vote_average}</div>
		</li>
	{/each}
</ul>

<style>
	li {
		list-style-type: none;
	}
	.movie-container {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		grid-row-gap: 2rem;
	}
	.movie-item {
		text-align: center;
	}
	.movie-image {
		width: 100%;
		max-width: 240px;
		object-fit: cover;
	}
</style>
