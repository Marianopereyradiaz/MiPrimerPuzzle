<script>
	// Inspired by https://svelte.dev/repl/810b0f1e16ac4bbd8af8ba25d5e0deff?version=3.4.2.
	import {flip} from 'svelte/animate';

    let baskets = [
    {
      "name": "Basket1",
      "items": []
    },
    {
      "name": "Basket2",
      "items": []
    },
    {
      "name": "Basket3",
      "items": []
    },
    {
      "name": "Basket4",
      "items": []
    },
    {
      "name": "Basket5",
      "items": []
    },
    {
      "name": "Basket6",
      "items": []
    },
    {
      "name": "Basket1b",
      "items": ["avion6.png"]
    },
    {
      "name": "Basket2b",
      "items": ["avion4.png"]
    },
    {
      "name": "Basket3b",
      "items": ["avion2.png"]
    },
    {
      "name": "Basket4b",
      "items": ["avion1.png"]
    },
    {
      "name": "Basket5b",
      "items": ["avion3.png"]
    },
    {
      "name": "Basket6b",
      "items": ["avion5.png"]
    },

  ];

	let hoveringOverBasket;
	
	function dragStart(event, basketIndex, itemIndex) {
		// The data we want to make available when the element is dropped
    // is the index of the item being dragged and
    // the index of the basket from which it is leaving.
		const data = {basketIndex, itemIndex};
   	event.dataTransfer.setData('text/plain', JSON.stringify(data));
	}
	
	function drop(event, basketIndex) {
		event.preventDefault();
    const json = event.dataTransfer.getData("text/plain");
		const data = JSON.parse(json);
		
		// Remove the item from one basket.
		// Splice returns an array of the deleted elements, just one in this case.
		const [item] = baskets[data.basketIndex].items.splice(data.itemIndex, 1);
		
    // Add the item to the drop target basket.
		baskets[basketIndex].items.push(item);
		baskets = baskets;
		
		hoveringOverBasket = null;
	}
</script>
<style>
	.hovering {
		border-color: orange;
	}
	li {
		background-color: lightgray;
		cursor: pointer;
		display: inline-block;
		margin:auto;
		padding: 0;
	}
	li:hover {
		background: orange;
		color: white;
	}
    ul {
		border: solid lightgray 1px;
		display: flex; /* required for drag & drop to work when .item display is inline */
		height: fit-content; /* needed when empty */
		width: fit-content;
        margin:0 auto;
        min-height: 235px;
        min-width: 200px;
        padding: 0;
	}

    .container {
        display:inline-grid;
        grid-template-columns: 200px 200px 200px;
        grid-template-rows: 235px 235px 235px;
        grid-gap: 0px;
        border: solid black 2px;
        padding:0;
        width: auto;
        height: auto;
    }

    .grid-item {
        display: inline; /* required for flip to work */
        margin:0;
        width:auto;
        height: auto;
        padding: 0;
    }

    img {
        height: fit-content;
        width: fit-content;
    }
	@media (min-width: 480px) {

	}
</style>

<svelte:head>
	<title>Mi Primer Puzzle</title>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-wEmeIV1mKuiNpC+IOBjI7aAzPcEZeedi5yW5f2yOq55WWLwNGmvvx4Um1vskeMj0" crossorigin="anonymous">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-p34f1UUtsS3wqzfto5wAAmdvj+osOnFyQFpp4Ua3gs/ZVWx6oOypYoCJhGGScy+8" crossorigin="anonymous"></script>
</svelte:head>
<p>Drag a fruit from one basket to another.</p>
<div class="container">
    {#each baskets as basket, basketIndex (basket)}
    <div animate:flip>
        <ul class:hovering={hoveringOverBasket === basket.name}
            on:dragenter={() => hoveringOverBasket = basket.name}
            on:dragleave={() => hoveringOverBasket = null}
            on:drop={event => drop(event, basketIndex)}
            ondragover="return false" >
            {#each basket.items as item, itemIndex (item)}
            <div class="grid-item" animate:flip>
                <li
                    draggable={true}
                    on:dragstart={event => dragStart(event, basketIndex, itemIndex)}
                    >
                        <img src="{item}" alt="">                   
                </li>
            </div>
            {/each}
        </ul>
    </div>
    {/each}

</div>


