<script>
    import Workout from './Workout.svelte';
    import { createEventDispatcher } from 'svelte';
    import { fade } from 'svelte/transition';

    export let name;
    export let description;
    export let workouts;

    const dispatch = createEventDispatcher();
    function addStatus(){
        dispatch('addStatus');
    }
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    div {
		text-align: center;
		background: #424242d8;
		width: 20vw;
		height: 50vh;
		margin: 0 1vw;
		border-radius: 15px;
    }
    .pepega {
        overflow-y: auto;   
    }
</style>
<div transition:fade>
    <button on:click={addStatus}>Add new</button>
	<h1>{name}</h1>
	<h3>{description}</h3>
    <div class="pepega">
        <ul>
            {#each workouts as workout}
                <Workout {...workout} />
            {/each}
        </ul>
    </div>
</div>