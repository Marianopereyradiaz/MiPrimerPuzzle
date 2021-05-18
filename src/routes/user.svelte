<style>
	.btn-primary {
		box-shadow: 0 0 8px 3px black;
		border: 1px solid black ;
		width: fit-content;
		font-size: x-large;
		background-color:powderblue;
		color:mediumvioletred;
		font-weight: bolder;
		border-radius: 10%;
	}

	form{
		background-color:mediumpurple;
		border-radius: 5%;
		width: 60vw;
		margin:auto;
		margin-top: 2%;
		margin-bottom: 5vh;
		font-weight: bolder;
		font-size: x-large;
		color:midnightblue;
		box-shadow: 0 0 8px 3px black;
		border: 1px solid black ;
		max-height: 100vh;
		max-width: 500px;
		min-width: 310px;
		padding:2%;
	}
	.form-group {
		max-width: 600px;
		width: fit-content;
		position:relative;
		margin: auto;
		padding: 5%;
		background-color:rgb(223, 190, 8);
		border-radius: 15%;	
		box-shadow: 0 0 8px 3px black;
	}

	@media (min-width: 480px) {

	}
</style>

<svelte:head>
	<title>Mi Primer Puzzle</title>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-wEmeIV1mKuiNpC+IOBjI7aAzPcEZeedi5yW5f2yOq55WWLwNGmvvx4Um1vskeMj0" crossorigin="anonymous">
	<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-p34f1UUtsS3wqzfto5wAAmdvj+osOnFyQFpp4Ua3gs/ZVWx6oOypYoCJhGGScy+8" crossorigin="anonymous"></script>
</svelte:head>
<div class="boton">
	<form>
		<div class="form-group">
		  <p><label for="formGroupExampleInput">NOMBRE</label></p>
		  <p><input type="text" class="form-control" id="formGroupExampleInput" placeholder="Tu Nombre"></p>
		</div>
		&nbsp;
		<div class="form-group">
		  <p><label for="formGroupExampleInput2">EDAD</label></p>
		  <p><input type="text" class="form-control" id="formGroupExampleInput2" placeholder="Tu Edad"></p>
		</div>
	</form>
	<p><a href="letters"><button type="button" class="btn btn-primary btn-lg">INGRESAR</button></a></p>
	<p><a href="."><button type="button" class="btn btn-primary btn-lg">VOLVER</button></a></p>	
</div>