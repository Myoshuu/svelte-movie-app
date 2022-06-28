<script>
	import { goto } from '$app/navigation';

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
			class="absolute bg-blue-600 font-bold text-white py-[3px] px-10 rounded-br-xl rounded-tr-xl"
			>Search</button
		>
	{/if}
</form>
