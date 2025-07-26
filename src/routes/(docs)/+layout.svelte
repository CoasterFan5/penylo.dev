<script lang="ts">
	import Sidebar from './Sidebar.svelte';
	import { MediaQuery } from 'svelte/reactivity';
	const large = new MediaQuery('min-width: 800px');

	const { children } = $props();

	const bannerInfo:
		| {
				title: string;
				url: string;
		  }
		| false = { title: 'Currency API Out Now!', url: '/currency' };

	let showSidebar = $state(large.current);
</script>

<div class="wrap">
	{#if bannerInfo}
		<a class="banner" href={bannerInfo.url}>
			{bannerInfo.title}
		</a>
	{/if}
	<div class="header">
		<button onclick={() => (showSidebar = !showSidebar)}>|||</button>
		<a href="/" class="title"> penylo.dev </a>
	</div>
	<div class="body">
		{#if showSidebar}
			<Sidebar overlaySidebar={!large.current} />
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
		height: 100vh;
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

	.banner {
		width: 100%;
		padding: 0.25rem;
		display: flex;
		align-items: center;
		justify-content: center;
		text-decoration: none;
		color: var(--text);
		background: var(--primary-25);
		transition: all cubic-bezier(0.455, 0.03, 0.515, 0.955) 0.1s;

		&:hover {
			background: var(--primary);
		}
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
