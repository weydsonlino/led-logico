<script lang="ts">
	import '../../style/reset.css';
	import '../../style/game.css';
	import Led from '../../components/Led.svelte';

	let led: boolean[][]=[
		[true, false, true],
		[false, true, false],
		[true, false, true],
	];
	let moves : number = 0;

	//Alterar o estado do LED clicado e dos LEDs adjacentes
	function toggleLed(rowIndex: number, colIndex: number){
		//altera o estado do LED clicado
		led[rowIndex][colIndex] = !led[rowIndex][colIndex];
		// Alterna o LED acima, se existir
		if (rowIndex > 0) {
			led[rowIndex-1][colIndex] = !led[rowIndex-1][colIndex];
		}
		// Alterna o LED abaixo, se existir
		if (rowIndex < 2) {
			led[rowIndex + 1][colIndex] = !led[rowIndex + 1][colIndex];
		}

		// Alterna o LED à esquerda, se existir
		if (colIndex > 0) {
			led[rowIndex][colIndex - 1] = !led[rowIndex][colIndex - 1];
		}

		// Alterna o LED à direita, se existir
		if (colIndex < 2) {
			led[rowIndex][colIndex + 1] = !led[rowIndex][colIndex + 1];
		}
		moves++;
	}

</script>

<body class="game-page">
	<header class="header-game">
		<nav class="game-bar">
			<a href="/"><button class="buttons">back</button></a>
			<button class="buttons-game"><i class="fi fi-br-rotate-left"></i></button>
		</nav>
	</header>
	<main class="game">
		<div id="container-game">
			{#each led as row , rowIndex}
				<div class="row-game">
				{#each row as col, colIndex}
						<Led state={led[rowIndex][colIndex]} toggle={() => toggleLed(rowIndex, colIndex)} />
				{/each}
				</div>
			{/each}
		</div>
		<footer class="game-footer">
			<h3 class="moves">MOVES : {moves}</h3>
			<div class="button-dica">
				<button class="buttons-game"><i class="fi fi-br-bulb"></i></button>
			</div>
		</footer>
	</main>
</body>
