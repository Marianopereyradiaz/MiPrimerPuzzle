<style>
	.btn-primary {
		box-shadow: 0 0 8px 3px black;
		border: 1px solid black ;
		width: 15vmax;
		font-size: xx-large;
		background-color:powderblue;
		color:mediumvioletred;
		font-weight: bolder;
		border-radius: 10%;
	}

	form{
		background-color:mediumpurple;
		padding: 2%;
		border-radius: 5%;
		width: 60vw;
		margin:auto;
		margin-bottom: 5vh;
		font-weight: bolder;
		font-size: xx-large;
		color:midnightblue;
		box-shadow: 0 0 8px 3px black;
		border: 1px solid black ;
		max-height: 100vh;
	}
	.form-group {
		width: 50vw;
		position:relative;
		margin: 5%;
		padding: 8%;
		font-weight: bold;
		background-color: white;
		border-radius: 15%;	
		border: 1px solid black ;
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
		  <label for="formGroupExampleInput">NOMBRE</label>
		  <input type="text" class="form-control" id="formGroupExampleInput" placeholder="Tu Nombre">
		</div>
		<div class="form-group">
		  <label for="formGroupExampleInput2">EDAD</label>
		  <input type="text" class="form-control" id="formGroupExampleInput2" placeholder="Tu Edad">
		</div>
	</form>
	<p><a href="."><button type="button" class="btn btn-primary btn-lg">INGRESAR</button></a></p>
	<p><a href="."><button type="button" class="btn btn-primary btn-lg">VOLVER</button></a></p>	
</div>