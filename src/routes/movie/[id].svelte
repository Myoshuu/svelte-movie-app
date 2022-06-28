<script context="module">
	export const load = async ({ fetch, params }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=bd4d05e79f3e765cbc73b27ff1a3d126`
		);
		const movieDetails = await res.json();
		return {
			props: { movieDetails }
		};
	};
</script>

<script>
	export let movieDetails;
</script>

<section class="my-[2rem] mx-[20%]">
	<div class="w-full">
		<img
			class="w-full rounded-xl object-cover"
			src={`https://image.tmdb.org/t/p/w500/${movieDetails.backdrop_path}`}
			alt=""
		/>
	</div>
	<div class="mt-5">
		<p class="font-bold text-2xl tracking-tighter mb-5">{movieDetails.original_title}</p>
		<p>{movieDetails.overview}</p>
		<div class="mt-10">
			<p><span>Release Date : </span>{movieDetails.release_date}</p>
			<p><span>Budget : </span>{movieDetails.budget}</p>
			<p><span>Rating : </span>{movieDetails.vote_average}</p>
			<p><span>Runtime : </span>{movieDetails.runtime} Minutes</p>
		</div>
	</div>
</section>

<style>
	span {
		font-weight: 600;
	}
</style>
