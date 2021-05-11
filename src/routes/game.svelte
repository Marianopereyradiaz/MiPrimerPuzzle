<script>

import { svg_element } from "svelte/internal";

</script>
<style>
	.btn{
		box-shadow: 0 0 8px 3px black;
		border: 1px solid black ;
		width: fit-content;
		font-size: x-large;
		background-color:powderblue;
		color:mediumvioletred;
		font-weight: bolder;
		border-radius: 10%;
	}

    .container {
        margin:auto;
        background-color:cornflowerblue;
        padding: 2%;
        box-shadow: 0 0 8px 3px black;
        width: fit-content;
        border-radius: 15%;
        max-width: 350px;
		min-width: 310px;
    }

    .ImgContainer {
        margin:auto;
        background-color:white;
        padding: 2%;
        box-shadow: 0 0 8px 3px black;
        width: fit-content;
        min-width: 320px;
        border-radius: 15%;
        max-width: 810px;
    }

    p{
        width: fit-content;
        color:white;
        font-weight: bolder;
    }

    .ImgFull {
        max-width: 800px;
        min-width: 320px;
        margin:auto;    
        opacity: 30%;   
        border: 1px solid black;
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

<br>
<div class="ImgContainer">
    <div class="ImgFull">
	    <img src="avionEntero.png" alt="full">
        <svg>
    </div>
</div>
<div class="container">
	<img src="avion1.png" alt="">
    <img src="avion2.png" alt="">
</div>
<br>
<div class="boton">
	<p><a href="letters"><button type="button" class="btn btn-primary btn-lg">SALIR</button></a></p>
    <p>Perderás la partida</p>	
</div>