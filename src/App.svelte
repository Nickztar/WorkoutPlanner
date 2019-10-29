<script>
	import Week from './Week.svelte';
</script>

<style>
	* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	}

	.days {
		display: flex;
		justify-content: center;
		margin-top: 20vh;
		color: aliceblue;
	}
</style>

<ul class="days">
	<Week/>
</ul>



