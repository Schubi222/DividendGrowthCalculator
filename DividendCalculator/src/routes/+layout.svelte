<script lang="ts">
	import { is_dark } from '$lib/stores/settings';
	import { is_loading, loading_error } from '$lib/stores/loading';
	import LoadingScreen from '../components/utils/LoadingScreen.svelte';
	import ErrorScreen from '../components/utils/ErrorScreen.svelte';
	import '/src/style/index.css';
</script>

<div class={`content ${$is_dark ? 'DARK' : 'LIGHT'}`}>
	{#if $loading_error}
		<ErrorScreen />
	{:else if $is_loading}
		<LoadingScreen />
	{:else}
		<slot />
	{/if}
</div>
