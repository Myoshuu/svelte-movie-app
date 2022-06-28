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

	export let movies;
</script>

<section class="mb-10">
	<PopularMovies {movies} />
	<div class="text-center my-10">
		<p class="text-xs">Copyright &copy; joe</p>
		<p class="text-sm text-slate-600">TMDB | Svelte | Dev Ed</p>
	</div>
</section>
