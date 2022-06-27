<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';
	import type { ListMovieResposne, Movie } from '../apis/movie';

	export const load: Load = async ({ fetch }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=${
				import.meta.env.VITE_TMDB_API_KEY
			}&language=en-US&page=1`
		);

		const data: ListMovieResposne = await res.json();
		if (res.ok) {
			console.log(data);
			return {
				props: {
					popularMovies: data.results
				}
			};
		} else {
			return {
				props: {}
			};
		}
	};
</script>

<script lang="ts">
	import PopularMovies from '../components/PopularMovies.svelte';
	export let popularMovies: Movie[];
</script>

<section>
	<PopularMovies {popularMovies} />
</section>
