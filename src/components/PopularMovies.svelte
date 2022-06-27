<script lang="ts">
	import type { Movie } from 'src/apis/movie';

	export let popularMovies: Movie[];
</script>

<ul class="grid lg:grid-cols-4 sm:grid-cols-3 gap-3">
	{#each popularMovies as movie}
		<li class="list-none">
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

