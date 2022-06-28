<script>
	import { goto } from '$app/navigation';
	import { fly } from 'svelte/transition';

	let search = '';

	const submitSearch = () => {
		goto(`/search/${search}`);
	};
</script>

<form on:submit|preventDefault={submitSearch} action="">
	<input
		class="py-[2px] px-2 border rounded-tl-lg rounded-bl-lg"
		type="text"
		name="search_movie"
		id=""
		placeholder="Search Movie"
		bind:value={search}
	/>
	{#if search}
		<button
			out:fly={{ y: 0, duration: 500 }}
			in:fly={{ y: -10, duration: 500 }}
			class="absolute bg-blue-600 font-bold text-white py-[3px] px-10 rounded-br-xl rounded-tr-xl"
			>Search</button
		>
	{/if}
	<p class="text-sm text-slate-500">go back to home just press "Movie App" text</p>
</form>
