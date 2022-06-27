<script>
	import Nav from '../components/Nav.svelte';

	import '../app.css';
</script>

<svelte:head>
	<title>Movie DB Svelte</title>
</svelte:head>

<Nav />
<div class="container mx-auto">
    <slot />
</div>
