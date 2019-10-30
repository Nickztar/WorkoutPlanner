<script>
    import { createEventDispatcher } from 'svelte';
    import { fade } from 'svelte/transition';
    const dispatch = createEventDispatcher();
    let dName;
    let dDescription;
    function add(){
        dispatch('add', {dName, dDescription});
    }
</script>

<style>
    div {
        position: absolute;
        top: 50%; 
        left: 50%;
        transform: translate(-50%, -50%);
        width: 35vw;
        height: 75vh;
        border-radius: 10px;
        display: grid;
        background: black;
    }
    input {
        width: 50%;
        height: 25%;
        margin: auto;
    }
</style>

<div transition:fade>
    <input type="text" bind:value={dName} placeholder="Workout name" required>
    <input type="text" bind:value={dDescription} placeholder="A good description for it" required>
    <button on:click={add}>Add this workout</button>
</div>
