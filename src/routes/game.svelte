<script>
	import { dndzone } from 'svelte-dnd-action';
	import { flip } from 'svelte/animate';

	let items = [
		{
			id: 1,
			text: 'avion1.png',
		},
		{
			id: 2,
			text: 'avion2.png',
		},
		{
			id: 3,
			text: 'avion3.png',
		},		{
			id: 4,
			text: 'avion4.png',
		},
		{
			id: 5,
			text: 'avion5.png',
		},
		{
			id: 6,
			text: 'avion6.png',
		},
	];
	
	const flipDurationMs = 200;
	let dragDisabled = true;
	
	const handleConsider = evt => {
		items = evt.detail.items;
	};
	const handleFinalize = evt => {
		items = evt.detail.items;
		// Ensure dragging is stopped on drag finish
		dragDisabled = true;
	};
	
		const startDrag = () => {
		dragDisabled = false;
	};
	const stopDrag = () => {
		dragDisabled = true;
	};

</script>

<style>
	div {
		position: relative;
		width: 200px;
		border: 1px solid black;
		margin: auto;
	}
	.handle {
		cursor: grab;
		position: absolute;
		width: 200px;
		height: 235px;
		margin:auto;
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




<section
	use:dndzone="{{ items, dragDisabled, flipDurationMs }}"
	on:consider="{handleConsider}"
	on:finalize="{handleFinalize}"
>
	{#each items as item (item.id)}
		<div animate:flip="{{ duration: flipDurationMs }}">
			<div class="handle" on:mousedown={startDrag} on:touchstart={startDrag} on:mouseup={stopDrag} on:touchend={stopDrag}/>
			<span><img src="{item.text}" alt=""></span>
  	</div>
	{/each}
</section>