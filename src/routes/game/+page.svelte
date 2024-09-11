<script lang="ts">
	import '../../style/reset.css';
	import '../../style/game.css';
	import Led from '../../components/Led.svelte';

	let led: boolean[][]=[
		[false, false, true],
		[false, true, true],
		[false, false, false],
	];
	let moves : number = 0;
	let victoryController : number = 9;
	let victory = false;
	shuffleArray(led);

	//Alterar o estado do LED clicado e dos LEDs adjacentes
	function toggleLed(rowIndex: number, colIndex: number){
		if (victory) return;
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
		checkVictory();
	}
	function gameReset(){
		led = [
			[true, false, true],
			[false, true, false],
			[true, false, true],
		];
		moves = 0;
		shuffleArray(led);
		victoryController = 9;
		victory = false;
	}
	// ENTENDER ISSOOOOOOO
	function shuffleArray(array: boolean[][]) {
		for (let i = array.length - 1; i > 0; i--) {
			for (let j = array[i].length - 1; j > 0; j--) {
				const k = Math.floor(Math.random() * (i + 1));
				const l = Math.floor(Math.random() * (j + 1));
				[array[i][j], array[k][l]] = [array[k][l], array[i][j]];
			}
		}
		return array;
	}
function checkVictory(){
	victoryController = 9;
		for (let i = 0; i < led.length; i++) {
			for (let j = 0; j < led[i].length; j++) {
				if (led[i][j] === true) {
					victory = false;
					break;
				}
				victoryController--;
			}
		}
		if (victoryController <= 0) {
			victory = true;
		}
	}

</script>

<body class="game-page">
	<header class="header-game">
		<nav class="game-bar">
			<a href="/"><button class="buttons">back</button></a>
			<button class="buttons-game" on:click={gameReset} ><i class="fi fi-br-rotate-left"></i></button>
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
			{#if victory}
				<h3 class="moves">Congratulations you won with {moves} moves</h3>
				<button class="buttons-game" on:click={gameReset}>Play Again</button>
			{/if}
		</footer>
	</main>
</body>
