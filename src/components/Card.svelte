<script>
	export let movie;
</script>

<section>
	<div>
		<a href={`/movie/${movie.id}`}>
			<img
				class="w-[100%] mb-5 object-cover rounded-xl hover:scale-105 transition-all"
				src={`https://image.tmdb.org/t/p/w500/${movie.poster_path}`}
				alt={movie.title}
			/>
		</a>
	</div>
	<p>{movie.title}</p>
	<p class="text-slate-500">{movie.release_date}</p>
</section>
