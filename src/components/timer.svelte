<script>
    import { onMount } from 'svelte';
	export let counter = 0;
	onMount(() => {
		const interval = setInterval(() => {
			counter = counter + 1;
		}, 1000);
		return () => clearInterval(interval);
	});
</script>

<script context="module">
	export function getCounter() {
	  return {counter};
	}
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
</style>
<div class="time">
<h1>TIEMPO</h1>
<h1 id="tag">
	{counter}
</h1>
</div>