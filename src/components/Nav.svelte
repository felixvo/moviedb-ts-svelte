<script>
	import Search from '../components/Search.svelte';
</script>

<nav class="bg-white border-gray-200 px-2 sm:px-4 py-2.5 rounded dark:bg-gray-800">
	<div class="container flex flex-wrap justify-between items-center mx-auto">
		<a href="/" class="flex items-center">
			<img src="/favicon.png" class="mr-3 h-6 sm:h-9" alt="MovieDB Logo" />
			<span class="self-center text-xl font-semibold whitespace-nowrap dark:text-white"
				>MovieDB</span
			>
		</a>
		<div class="flex md:order-2">
			<Search />
		</div>
		<div
			class="hidden justify-between items-center w-full md:flex md:w-auto md:order-1"
			id="mobile-menu-3"
		>
			<ul class="flex flex-col mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-sm md:font-medium">
				<li>
					<a
						href="/"
						class="block py-2 pr-4 pl-3 text-white bg-blue-700 rounded md:bg-transparent md:text-blue-700 md:p-0 dark:text-white"
						aria-current="page">Home</a
					>
				</li>
			</ul>
		</div>
	</div>
</nav>
