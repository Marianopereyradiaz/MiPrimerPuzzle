<script>
	import {draggable} from '../components/dragdrop.js'
	import {crossfade} from 'svelte/transition'
	import {quintOut, elasticOut} from 'svelte/easing'
	import { flip } from 'svelte/animate';
	import { onInterval } from '../components/utils.js';
	import { user } from "../components/user.js";

	let time;
	let seconds = 0;
	onInterval(() => seconds += 1, 1000);
	
	const shelf = [null, null, null, null, null,null]
	const cart = [{id: 5, name: 'avion5.png'},{id: 1, name: 'avion1.png'}, {id: 6, name: 'avion6.png'}, {id: 2, name: 'avion2.png'},{id: 3, name: 'avion3.png'},{id: 4, name: 'avion4.png'}]
		
	function putInShelf(item, index) {
		const oldItem = shelf[index]
		const oldShelfIndex = shelf.indexOf(item)	
		 if (cart.indexOf(item) !== -1) cart.splice(cart.indexOf(item), 1)
		if (oldShelfIndex !== -1) shelf[oldShelfIndex] = oldItem
		else if (oldItem) cart.push(oldItem)
		 shelf[index] = item;
		cart = cart
		if (index+1==item.id)
		shelfcomplete++;
	}
		
	function putInCart(item) {
		if (cart.indexOf(item) !== -1) cart.splice(cart.indexOf(item), 1)
	  if (shelf.indexOf(item) !== -1) shelf[shelf.indexOf(item)] = null
		cart.push(item)
		cart = cart
		if (index+1==item.id)
		shelfcomplete--;
	}
	
	const [send, receive] = crossfade({
	  duration: d => 600,
	  easing: elasticOut,
	  fallback(node, params) {
		const style = getComputedStyle(node);
		const transform = style.transform === 'none' ? '' : style.transform;
	
		return {
		  duration: 600,
		  easing: quintOut,
		  css: t => `
			transform: ${transform} scale(${t});
			opacity: ${t}
		  `
		};
	  }
	});
	
	let shelfcomplete=0;

	</script>
	
	<style>
			.time{
		padding: 2%;
		background-color: white;
		margin: 0 auto;
		width: min-content;
		box-shadow: 5px 10px 18px black;
		margin: auto;
		border-radius: 5%;
	}

	.settime{
		display: none;
	}

		.shelf{
			display: inline-grid;
			grid-template-columns: auto auto auto;
			position: relative;
			margin-top:2%;
			margin-bottom: 2%;
			box-shadow: 5px 10px 18px black;
		}

		.slot {
			position: relative;
			display: inline-block;
			width: 200px;
			height: 235px;
			vertical-align: top;
			border:solid black 1px;
			background-color: white;

		}
		.cart {
			position: relative;
			min-height: 235px;
			min-width: 200px;
			margin: auto;
			border: solid 1px black;
		}
		.item {
			height: fit-content;
			position: relative;
			display: inline-block;
			margin: auto;
		}
		.slot .item {
			position: relative;

		}
		:global(.dragged) {
		  pointer-events: none;
			z-index: 100;
		}
	</style>
	
<svelte:head>
	<title>Mi Primer Puzzle</title>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-wEmeIV1mKuiNpC+IOBjI7aAzPcEZeedi5yW5f2yOq55WWLwNGmvvx4Um1vskeMj0" crossorigin="anonymous">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-p34f1UUtsS3wqzfto5wAAmdvj+osOnFyQFpp4Ua3gs/ZVWx6oOypYoCJhGGScy+8" crossorigin="anonymous"></script>
</svelte:head>

{#if shelfcomplete<6}
<div class="shelf">
	{#each shelf as item, index }
		<div class="slot" on:dropped={(e) => putInShelf(e.detail, index)}>
			{#if item}
				{#each [item] as item (item.id)}				
					<div class="item" use:draggable={{data: item, targets: ['.cart', '.slot', '.slot .item']}} in:receive={item.id} out:send={item.id} on:dropped={(e) => putInShelf(e.detail, index)}>
						<img src="{item.name}" alt="">						
					</div>					
				{/each}
			{/if}
		</div>
	{/each}
</div>
<br>
<div class="cart" on:dropped={(e) => putInCart(e.detail)}>
	{#each cart as item, index (item.id)}
		<div class="item" animate:flip use:draggable={{data: item, targets: ['.slot', '.slot .item']}} in:receive={item.id} out:send={item.id}>
			<img src="{item.name}" alt="">	
		</div>
	{/each}
</div>
<br>
<div class="time">
	Tiempo
	{seconds} 
</div>
<div class="settime">
	{time=seconds}
</div>

{:else}
	<h1 style="background-color: coral;">GANASTE {$user.name} de {$user.age} años!</h1>
	<h2 style="color:white;">Tiempo: {time} segundos! </h2>
{/if}