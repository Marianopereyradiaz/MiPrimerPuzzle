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
        margin:auto;
	}

    h1 {
        font-weight: bold;
        font-size: xx-large;
    }
    header{
        background-color:orange;
        padding:3%;
        border-radius: 25%;
        width: fit-content;
        position: relative;
        margin: auto;
        text-align: center;
        box-shadow: 0 0 8px 3px black;
        max-width: 500px;
		min-width: 310px;
    }

    .container {
        margin:auto;
        background-color:cornflowerblue;
        padding: 2%;
        box-shadow: 0 0 8px 3px black;
        margin: auto;
        width: fit-content;
        border-radius: 15%;
        max-width: 350px;
		min-width: 310px;
    }

    .boton{
        width: fit-content;
        margin-left: auto;
        margin-right: auto;
        
    }
	@media (min-width: 480px) {

	}
</style>

<svelte:head>
	<title>Mi Primer Puzzle</title>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-wEmeIV1mKuiNpC+IOBjI7aAzPcEZeedi5yW5f2yOq55WWLwNGmvvx4Um1vskeMj0" crossorigin="anonymous">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-p34f1UUtsS3wqzfto5wAAmdvj+osOnFyQFpp4Ua3gs/ZVWx6oOypYoCJhGGScy+8" crossorigin="anonymous"></script>
</svelte:head>
<header>
    <h1>ELEGIR DIFICULTAD</h1>
</header>
<br>
<div class="container">
    <p><a href="game" class="btn btn-success btn-lg active" role="button" aria-pressed="true">FACIL</a></p>
    <p><a href="game" class="btn btn-warning btn-lg active" role="button" aria-pressed="true">MEDIO</a></p>
    <p><a href="game" class="btn btn-danger btn-lg active" role="button" aria-pressed="true">DIFICIL</a></p>
</div>
<br>
<div class="boton">
	<p><a href="letters"><button type="button" class="btn btn-primary btn-lg">VOLVER</button></a></p>	
</div>