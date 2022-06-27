<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';

	export const load: Load = async ({ fetch, params }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=${
				import.meta.env.VITE_TMDB_API_KEY
			}&language=en-US`
		);
		const data = await res.json();
		if (res.ok) {
			return {
				props: {
					movie: data
				}
			};
		}
		return {};
	};
</script>

<script lang="ts">
	import type { Movie } from 'src/apis/movie';
	export let movie: Movie;
</script>

{#if movie}
	<div>
		<img
			class="w-full"
			src={'https://image.tmdb.org/t/p/original/' + movie.backdrop_path}
			alt={movie.title}
		/>
		<div>{movie.title}</div>
		<p>{movie.overview}</p>
		<div>{movie.vote_average}</div>
	</div>
{:else}
	<div>loading data</div>
{/if}
