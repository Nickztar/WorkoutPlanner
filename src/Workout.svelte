<script>
	export let name;
	export let description
</script>

<style> 
	* {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    div {
		width: 85%;
		margin: auto;
		margin-top: 2vh;
		background: black;
		border-radius: 15px;
	}
</style>

<div>
	<h1>{name}</h1>
	<h3>{description}</h3>
</div>