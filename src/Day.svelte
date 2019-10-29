<script>
    import Workout from './Workout.svelte';
    export let name;
    export let description;
    export let workouts;
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    div {
		text-align: center;
		background: blue;
		width: 20vw;
		height: 50vh;
		margin: 0 1vw;
		border-radius: 15px;
	}
</style>
<div>
	<h1>{name}</h1>
	<h3>{description}</h3>
    <ul>
        {#each workouts as workout}
            <Workout {...workout} />
        {/each}
    </ul>
</div>