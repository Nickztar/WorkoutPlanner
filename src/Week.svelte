<script>
    import Day from './Day.svelte';
    import Create from './Create.svelte';
    import { db, fvBase } from './firebase';
    import { collectionData } from 'rxfire/firestore';
    import { startWith } from 'rxjs/operators';

    let addNew = false;

    const query = db.collection('week');

    const weeks = collectionData(query, 'id').pipe(startWith([]));

    function add(event){
        addNew = false;
        const { dName, dDescription } = event.detail;
        const document = db.collection('week').doc('azhcvPrhRxqajbI6VzXQ');
        document.update({workouts: fvBase.FieldValue.arrayUnion({name: dName, description: dDescription})});
    }
    function status(){
        addNew = true;
    }
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

{#if addNew}
    <Create on:add = {add}/>
{/if}
<ul class="days">
    {#each $weeks as week}
        <Day on:addStatus={status} {...week}/>
    {/each}
</ul>


     <!-- else if content here -->
<!-- <Create on:add = {add}/>
{#each $weeks as week}
    <Day {...week}/>
{/each} -->