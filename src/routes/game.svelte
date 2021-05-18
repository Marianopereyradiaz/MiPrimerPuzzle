<script>
	import Draggable from '../components/draggable.svelte';
	export let images = ["avion1.png","avion2.png","avion3.png","avion4.png","avion5.png","avion6.png"];
</script>
<style>

	img {
		position: relative;
		background-color: white;
  		height: auto;
		min-width: 50px;
		max-width: 120px;
	}
	@media (min-width: 480px) {

	}
</style>

<svelte:head>
	<title>Mi Primer Puzzle</title>
	<link href="draganddrop.css" rel="stylesheet">
	<script src="//code.jquery.com/jquery.min.js"></script>
	<script src="draganddrop.js"></script>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-wEmeIV1mKuiNpC+IOBjI7aAzPcEZeedi5yW5f2yOq55WWLwNGmvvx4Um1vskeMj0" crossorigin="anonymous">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-p34f1UUtsS3wqzfto5wAAmdvj+osOnFyQFpp4Ua3gs/ZVWx6oOypYoCJhGGScy+8" crossorigin="anonymous"></script>
</svelte:head>

{#each images as image}
	<Draggable top={Math.floor(Math.random() * 300)} left={Math.floor(Math.random() * 300)}>
		<img src="{image}" alt="">
	</Draggable>
{/each}





