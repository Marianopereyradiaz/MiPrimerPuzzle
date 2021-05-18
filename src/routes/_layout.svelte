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
        height:97vh;
        text-align: center;
		padding:0;
		margin: 0;
		min-height:70vh;
	}
</style>


<main>
	<Nav {segment}/>
	<slot></slot>	
</main>
<Footer {segment}/>
