<script lang="ts">
	export let buttonText: string;
	export let onEvent: (data: string) => void;
	const handleClick = () => {
		onEvent(buttonText);
	};
</script>

<button on:click={handleClick}>{buttonText}</button>

<style>
</style>
