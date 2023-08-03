<script>
	import DateForm from '../components/dateForm.svelte';
	import WeekGrid from '../components/weekGrid.svelte';
</script>

<svelte:head>
	<title>Your Life In Weeks</title>
	<meta name="description" content="Visualize your whole life in weeks." />
</svelte:head>

<section>
	<h1 class="text-3xl font-bold text-white text-center mt-10">
		Your Life In Weeks
	</h1>
	<p class="text-white text-center mt-5">
		Visualize your whole life in weeks.
	</p>
	<DateForm />
	<WeekGrid />

</section>

<style lang="postcss">
	/* :global(html) {
	  background-color: theme(colors.black);
	} */
</style>
