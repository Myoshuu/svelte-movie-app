<script context="module">
	export const load = async ({ fetch }) => {
		const res = await fetch(
			'https://api.themoviedb.org/3/movie/popular?api_key=bd4d05e79f3e765cbc73b27ff1a3d126'
		);
		const data = await res.json();
		return {
			props: {
				movies: data.results
			}
		};
	};
</script>

<script>
	// Components
	import PopularMovies from '../components/PopularMovies.svelte';

	import { fly } from 'svelte/transition';

	export let movies;
</script>

<section class="mb-10" in:fly={{ y: 50, duration: 500 }} out:fly={{ duration: 500 }}>
	<PopularMovies {movies} />
</section>
