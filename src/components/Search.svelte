<script lang="ts">
	import { goto } from '$app/navigation';

	let searchQuery = '';

	const submitSearch = () => {
		goto('/search/' + searchQuery);
	};
</script>

<form on:submit|preventDefault={submitSearch}>
	<input type="text" bind:value={searchQuery} name="search query" />

	<button type="submit" disabled={!searchQuery}>Search</button>
</form>
