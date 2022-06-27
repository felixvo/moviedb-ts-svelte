<script context="module">
	// {
	//     adult: false,
	//     backdrop_path: '/9bbxqz1iPEfZN9Xi2ZjJhkp5JRo.jpg',
	//     genre_ids: [ 16, 878, 28 ],
	//     id: 610150,
	//     original_language: 'ja',
	//     original_title: 'ドラゴンボール超：スーパーヒーロー',
	//     overview: 'The Red Ribbon Army, an evil organization that was once destroyed by Goku in the past, has been reformed by a group of people who have created new and mightier Androids, Gamma 1 and Gamma 2, and seek vengeance against Goku and his family.',
	//     popularity: 1643.443,
	//     poster_path: '/rugyJdeoJm7cSJL1q4jBpTNbxyU.jpg',
	//     release_date: '2022-06-11',
	//     title: 'Dragon Ball Super: Super Hero',
	//     video: false,
	//     vote_average: 8.4,
	//     vote_count: 46
	//   }
	// type Movie = {
	// 	id: Number;
	// 	title: String;
	// 	poster_path: String;
	// 	backdrop_path: String;
	// 	release_date: String;
	// };

	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_TMDB_API_KEY}&language=en-US&page=1`
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

<script>
	import Search from '../components/Search.svelte';
	import PopularMovies from '../components/PopularMovies.svelte';
	export let popularMovies;
</script>

<section>
	<Search />
	<PopularMovies {popularMovies} />
</section>
