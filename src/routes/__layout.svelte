<script>
	import Navbar from '../components/Navbar.svelte';

	import '../app.css';
</script>

<svelte:head>
	<title>Movie App</title>
</svelte:head>

<Navbar />
<slot />
