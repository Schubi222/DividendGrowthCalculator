<script lang="ts">
	import NumberInput from '../utils/NumberInput.svelte';
	import { currency_list } from '$lib/data/currencies';

	const selects = [
		{ label: 'Currency', value: '€', select_from: currency_list },
		{ label: 'Investment', value: 'Monthly', select_from: ['Monthly', 'Yearly'] },
		{ label: 'Taxable', value: true, select_from: [true, false] },
		{ label: 'Drip', value: true, select_from: [true, false] },
		{
			label: 'Dividend Payment',
			value: 'Yearly',
			select_from: ['Yearly', 'Semi-yearly', 'Quarterly', 'Monthly']
		}
	];
	const numbers = [
		{ label: 'Initial Investment', value: 10000, input_error: '', symbol: '€', range: false },
		{ label: 'Monthly Investment', value: 1000, input_error: '', symbol: '€', range: false },
		{ label: 'Annual Dividend Yield', value: 2.5, input_error: '', symbol: '%', range: true },
		{ label: 'Dividend Tax Rate', value: 27.5, input_error: '', symbol: '%', range: false },
		{
			label: 'Expected Annual Dividend Growth (CAGR)',
			value: 10,
			input_error: '',
			symbol: '%',
			range: false
		},
		{
			label: 'Expected Annual Share Price Appreciation',
			value: 10,
			input_error: '',
			symbol: '%',
			range: false
		},
		{ label: 'Years Invested', value: 20, input_error: '', symbol: 'Years', range: false }
	];

	$: numbers[0].symbol = selects[0].value as string;
	$: numbers[1].symbol = selects[0].value as string;
	$: numbers[1].label = selects[1] + ' Investment';
</script>

<div class="Inputs-Container">
	{#each numbers as { label, value, input_error, symbol }}
		<NumberInput {label} {symbol} bind:value bind:input_error />
	{/each}
</div>
