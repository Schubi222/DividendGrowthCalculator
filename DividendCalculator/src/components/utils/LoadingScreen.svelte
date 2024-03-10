<script lang="ts">
	import { Circle2 } from 'svelte-loading-spinners';
</script>

<div class="Spinner-Container">
	<Circle2 size="120" colorOuter="#1a4a72" colorCenter="#3083c7" colorInner="#a9d4f6" unit="px" />
	<div class="Spinner-Container__text">Loading...</div>
</div>

<style lang="scss">
	.Spinner-Container {
		display: flex;
		width: 100%;
		margin: auto;
		height: 100vh;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		gap: 30px;
		&__text {
			font-size: 20px;
		}
	}
</style>
