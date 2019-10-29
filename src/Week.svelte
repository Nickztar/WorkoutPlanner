<script>
    import Day from './Day.svelte';
    import { db } from './firebase';
    import { collectionData } from 'rxfire/firestore';
    import { startWith } from 'rxjs/operators';


    const query = db.collection('week');

    const weeks = collectionData(query, 'id').pipe(startWith([]));

</script>

<style>
</style>

{#each $weeks as week}
    <Day {...week}/>
{/each}