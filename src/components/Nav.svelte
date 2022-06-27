<script>
	import Search from '../components/Search.svelte';
</script>

<nav>
	<div class="nav-left">
		<ul>
			<li>
				<a href="/">Popular</a>
			</li>
		</ul>
	</div>
	<div class="nav-right">
		<ul>
			<li>
				<Search />
			</li>
		</ul>
	</div>
</nav>

<style>
	nav {
		background: green;
		padding: 15px;
	}
	nav ul {
		list-style-type: none;
		margin: 0;
		padding: 0;
		overflow: hidden;
	}

	nav a {
		display: block;
		max-width: 200px;
	}

	.nav-left {
		float: left;
	}

	.nav-left ul li {
		float: left;
	}

	.nav-right ul li {
		float: right;
	}
</style>
