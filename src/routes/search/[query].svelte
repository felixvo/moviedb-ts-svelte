<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';
	import type { ListMovieResposne } from 'src/apis/movie';

	export const load: Load = async ({ fetch, params }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=${
				import.meta.env.VITE_TMDB_API_KEY
			}&query=${params.query}&language=en-US&page=1`
		);
		const data: ListMovieResposne = await res.json();
		if (res.ok) {
			return {
				props: {
					popularMovies: data.results
				}
			};
		}
	};
</script>

<script lang="ts">
	type Movie = {
		id: String;
		title: String;
	};
	import PopularMovies from '../../components/PopularMovies.svelte';
	export let popularMovies: Movie[];
</script>

<section>
	<PopularMovies {popularMovies} />
</section>
