<script context="module" lang="ts">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=361122f735a0c3d01c0ff9b69a94ff26&query=${params.query}&language=en-US&page=1`
		);
		const data = await res.json();
		if (res.ok) {
			return {
				props: {
					popularMovies: data.results
				}
			};
		}
	}
</script>

<script lang="ts">
	type Movie = {
		id: String
		title: String
	}
	import PopularMovies from '../../components/PopularMovies.svelte';
	export let popularMovies: Movie[]
</script>

<section>
	<PopularMovies {popularMovies} />
</section>
