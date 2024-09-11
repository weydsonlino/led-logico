<script lang="ts">
	import '../style/game.css'
	export let state: boolean;
	export let toggle: () => void;
</script>
<!-- O estilo do LED muda com base no estado (ligado/desligado) -->
<div class="{state ? 'rectangle-on-game' : 'rectangle-off-game'}" on:click={toggle}></div>
