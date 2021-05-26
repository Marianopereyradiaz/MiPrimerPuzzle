<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';
	export let segment;
</script>

<style>
	main {
		position: relative;
		background-image: url("background.jpg");
        background-size: cover;
        background-repeat: no-repeat;
        width: 100vw;
        height:100vmax;
        text-align: center;
		padding:0;
		margin: 0;
		min-height:70vh;
		max-height: max-content;
	}
</style>


<main>
	<Nav {segment}/>
	<slot></slot>	
</main>
<Footer {segment}/>
