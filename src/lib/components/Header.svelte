<script lang="ts">
	import { AppBar } from '@skeletonlabs/skeleton';
	import { page } from '$app/stores';

	$: urlPath = $page.url.pathname;
</script>

<AppBar shadow="shadow-2xl">
	<svelte:fragment slot="lead">
		{#if urlPath !== '/'}
			<button
				class="btn back-btn jiggle"
				title="Back"
				on:click={() => {
					history.back();
				}}
			>
				<img src="/icons/icon-arrow-light.svg" alt="" class="rotate-180 cursor-pointer" />
			</button>
		{/if}

		<a href="/" class="link link--zoomies">
			<strong class="text-xl uppercase">SvelteKit Template</strong>
		</a>
	</svelte:fragment>

	<svelte:fragment slot="trail">
	</svelte:fragment>
</AppBar>

<style lang="scss">
	.btn.back-btn {
		padding: 0;
		height: 100%;
		margin-right: 0.5rem;

		img {
			height: 2.2rem;
		}
	}
</style>
