<script lang="ts">
	export let state: boolean;
	export let toggle: () => void;
</script>
<!-- O estilo do LED muda com base no estado (ligado/desligado) -->
<div class="{state ? 'rectangle-on' : 'rectangle-off'}" on:click={toggle}></div>
