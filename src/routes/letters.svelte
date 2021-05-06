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

    h1 {
        font-weight: bold;
        font-size: xx-large;
    }
    header{
        background-color:rgb(219, 236, 58);
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
        background-color:rgb(12, 209, 110);
        padding: 2%;
        box-shadow: 0 0 8px 3px black;
        margin: auto;
        width: fit-content;
        border-radius: 15%;
        max-width: 350px;
		min-width: 310px;
    }

    p{
        width: fit-content;
    }

    .btn-circle.btn-xl {
            width: 70px;
            height: 70px;
            padding: 10px 16px;
            border-radius: 35px;
            font-size:xx-large;
            text-align: center;
            background-color:rgb(152, 130, 228);
            color:rgb(62, 228, 62);
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
    <h1>¿Con cuál letra vas a jugar?</h1>
</header>
<br>
<div class="container">
    <p><a href="difficulty" class="btn btn-secondary btn-circle btn-xl" role="button" aria-pressed="true">A</a></p>
    <p><a href="difficulty" class="btn btn-secondary btn-circle btn-xl" role="button" aria-pressed="true">E</a></p>
    <p><a href="difficulty" class="btn btn-secondary btn-circle btn-xl" role="button" aria-pressed="true">I</a></p>
    <p><a href="difficulty" class="btn btn-secondary btn-circle btn-xl" role="button" aria-pressed="true">O</a></p>
    <p><a href="difficulty" class="btn btn-secondary btn-circle btn-xl" role="button" aria-pressed="true">U</a></p>
</div>
<br>
<div class="boton">
	<p><a href="user"><button type="button" class="btn btn-primary btn-lg">VOLVER</button></a></p>	
</div>