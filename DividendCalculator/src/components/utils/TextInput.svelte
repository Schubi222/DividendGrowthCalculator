<script lang="ts">
	export let value: string;
	export let label: string;
	export let input_error: string;
</script>

<div class="Input-Container">
	<div class="input__label">{label}</div>
	<div class="input__error">{input_error}</div>
	<input type="text" bind:value />
</div>
