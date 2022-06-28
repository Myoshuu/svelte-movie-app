<script>
	import Navbar from '../components/Navbar.svelte';

	import '../app.css';
</script>

<svelte:head>
	<title>Movie App</title>
</svelte:head>

<Navbar />
<slot />
<div class="text-center my-10">
	<p class="text-xs">Copyright &copy; joe</p>
	<p class="text-sm text-slate-600">TMDB | Svelte | Dev Ed</p>
</div>
