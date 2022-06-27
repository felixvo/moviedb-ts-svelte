<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=361122f735a0c3d01c0ff9b69a94ff26&language=en-US`
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
	}
</script>

<script>
	export let movie;
</script>

{#if movie}
	<div>
		<img src={'https://image.tmdb.org/t/p/original/' + movie.backdrop_path} alt={movie.title} />
		<p>{movie.id}</p>
		<p>{movie.title}</p>
	</div>
{:else}
	<div>loading data</div>
{/if}
