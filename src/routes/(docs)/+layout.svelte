<script lang="ts">
	import Sidebar from './Sidebar.svelte';
	import { MediaQuery } from 'svelte/reactivity';
	const large = new MediaQuery('min-width: 800px');

	const { children } = $props();

	let showSidebar = $state(large.current);
</script>

<div class="wrap">
	<div class="header">
		<button onclick={() => (showSidebar = !showSidebar)}>|||</button>
		<a href="/" class="title"> penylo.dev </a>
	</div>
	<div class="body">
		{#if showSidebar}
			<Sidebar overlaySidebar={!large.current} closeSidebar={() => (showSidebar = false)} />
		{/if}
		<div class="content">
			<div class="content-inner">
				{@render children?.()}
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	.wrap {
		width: 100%;
		height: 100dvh;
		overflow: hidden;
		display: flex;
		flex-direction: column;
	}

	.header {
		padding: 1rem 1rem;
		font-family: var(--font-mono);
		border-bottom: 1px solid var(--text-25);
	}

	.title {
		color: var(--text);
		font-weight: 400;
		font-size: 1.2rem;
		text-decoration: none;

		&:hover {
			color: var(--primary);
		}
	}

	.body {
		padding: 0;
		display: flex;
		flex-direction: row;
		height: 100%;
		overflow: hidden;
		position: relative;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: start;
		width: 100%;
		padding: 0.25rem;
		height: 100%;
		flex-grow: 1;
		overflow-y: auto;
		padding: 0 1rem;
	}

	.content-inner {
		width: 100%;
		max-width: 80ch;
		padding-bottom: 10rem;
	}

	button {
		all: unset;
		aspect-ratio: 1/1;
		transform: rotate(90deg);
		background: transparent;
		color: var(--text);
		font-kerning: 0pt;
		letter-spacing: -3pt;
		cursor: pointer;

		&:hover {
			color: var(--primary);
		}
	}
</style>
