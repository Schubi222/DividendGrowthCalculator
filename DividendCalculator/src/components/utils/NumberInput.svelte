<script lang="ts">
	export let value: number;
	export let label: string;
	export let input_error: string;
	export let symbol: string;
	const MAX = 999999999999;
	// export let rules;
	const enforceRules = () => {
		if (value > MAX)
			value = MAX; //TODO: MAKE THIS A BETTER UX
		else if (value < 0) value = 0;
		else if (value % 1 !== 0) value = +value.toFixed(2);
	};
</script>

<div class="Input-Container">
	<div class="input__label">{label}</div>
	<div class="input__error">{input_error}</div>
	<div class="input__symbol">{symbol}</div>
	<input class="input__input" type="number" bind:value on:input={() => enforceRules()} />
</div>

<style lang="scss">
	.Input-Container {
		width: 100%;
		max-width: 300px;
		height: 110px;
		position: relative;

		box-sizing: border-box;
		padding: 10px;

		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: flex-start;

		font-size: 20px;
		.input__label {
			color: var(--grey-1);
			padding-bottom: 10px;
		}
		.input__symbol {
			position: absolute;
			left: 20px;
			height: 20px;
			width: 20px;
			font-size: 30px;
			top: 50%;
			color: var(--grey-4);
		}
		.input__input {
			border-radius: 5px;
			outline: none;
			//border: none;
			padding: 10px 30px;
			width: 260px;
			height: 50px;
			font-size: 18px;
			text-align: right;
			box-sizing: border-box;
			color: var(--grey-2);
			background: var(--grey-9);
			border: 1px solid var(--grey-7);
		}
	}
</style>
