<script lang="ts">
	import '../../style/reset.css';
	import '../../style/globals.css';
	import Header from '../../components/header.svelte';
</script>

<body class="pages">
	<Header />
	<main class="pages">
		<h3 class="tittle">How To Play</h3>
		<div class="container-text">
			<p class="text">
				This is a simple puzzle game. The goal is to turn off all the lights.

				Tap a button. The neighboring buttons will also turn on or off, depending on their
				previous state.
			</p>
		</div>
		<div class="box">
			<button class="rectangle-off"></button>
			<button class="rectangle-on"></button>
			<button class="rectangle-off"></button>
			<button class="rectangle-on"></button>
			<button class="rectangle-off"></button>
			<button class="rectangle-on"></button>
			<button class="rectangle-off"></button>
			<button class="rectangle-on"></button>
			<button class="rectangle-off"></button>
		</div>
		<div class="container-text htp">
			<p class="text">
				This Website is a remake of the original Lights Out handheld game that was manufactured by
				Tiger Electronics. Here's a <a
					class="link"
					href="https://en.wikipedia.org/wiki/Lights_Out_(game)"
					target="_blank">more detailed description.</a
				>
			</p>
		</div>
	</main>
</body>
