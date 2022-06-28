<script>
	import Card from './Card.svelte';
	import Search from './Search.svelte';

	export let movies;
</script>

<section>
	<div class="flex justify-center items-center">
		<div class="w-10/12">
			<Search />

			<h3 class="font-bold py-5">Popular Movies</h3>
			<div class="movie gap-x-8 gap-y-10">
				{#each movies as movie}
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
