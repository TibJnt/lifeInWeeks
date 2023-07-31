<script>
	import "../app.css";
</script>

<div class="app">

	<main>
		<slot />
	</main>

</div>

<style lang="postcss">
	:global(html) {
	  background-color: theme(colors.black);
	}
</style>
