<script lang="ts">
	import '../../style/reset.css';
	import '../../style/globals.css';
</script>

<body class="pages game-page">
	<header class="header-game">
		<nav class="game-bar">
			<a href="/"><button class="buttons">back</button></a>
			<button class="buttons"><i class="fi fi-br-rotate-left"></i></button>
		</nav>
	</header>
	<main class="game">
		<div id="container-game">
			<div class="row-game">
				<button class="rectangle-off"></button><button class="rectangle-on"></button><button
					class="rectangle-off"
				>
				</button>
			</div>
			<div class="row-game">
				<button class="rectangle-on"></button><button class="rectangle-on"></button><button
					class="rectangle-on"
				>
				</button>
			</div>
			<div class="row-game">
				<button class="rectangle-off"></button><button class="rectangle-on"></button><button
					class="rectangle-off"
				>
				</button>
			</div>
		</div>
		<footer class="game-footer">
			<h3 class="moves">MOVES : 0</h3>
			<div class="button-dica">
				<button class="buttons dica"><i class="fi fi-br-bulb"></i></button>
			</div>
		</footer>
	</main>
</body>
