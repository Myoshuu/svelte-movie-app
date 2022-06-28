<script context="module">
	export const load = async ({ fetch, params }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=bd4d05e79f3e765cbc73b27ff1a3d126&language=en-US&query=${params.id}&page=1&include_adult=false`
		);
		const data = await res.json();
		return {
			props: {
				searchMovie: data.results
			}
		};
	};
</script>

<script>
	import Search from '../../components/Search.svelte';
	import Card from '../../components/Card.svelte';

	export let searchMovie;
</script>

<section>
	<div class="flex justify-center items-center">
		<div class="w-10/12">
			<Search />
			<div class="movie mt-10 gap-x-8 gap-y-10">
				{#each searchMovie as movie}
					<Card {movie} />
				{/each}
			</div>
		</div>
	</div>
</section>

<style>
	.movie {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
	}
</style>
