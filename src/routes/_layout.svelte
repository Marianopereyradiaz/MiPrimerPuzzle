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
        height: 100vh;
        text-align: center;
		padding:2%;
		margin: 0;
	}
</style>

<Nav {segment}/>
<main>
	<slot></slot>
</main>
<Footer {segment}/>
