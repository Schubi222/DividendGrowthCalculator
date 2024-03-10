<script lang="ts">
	import { loading_error } from '$lib/stores/loading';
</script>

<div class="Error-Container">
	<h1 class="Error-Container__heading">An Error Occurred!</h1>
	<div class="Error-Container__body">{$loading_error}</div>
	<button class="Error-Container__btn" on:click|preventDefault={()=>window.location.reload()}>Try again!</button>
</div>