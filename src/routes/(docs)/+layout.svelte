<script lang="ts">
	import Sidebar from './Sidebar.svelte';

	const { children } = $props();

	const bannerInfo:
		| {
				title: string;
				url: string;
		  }
		| undefined = undefined;
</script>

<div class="wrap">
	<div class="header">
		<a href="/" class="title"> penylo.dev </a>
	</div>
	<div class="body">
		<Sidebar />
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
		display: flex;
		flex-direction: column;
	}

	.header {
		padding: 1rem 3rem;
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
		padding: 0 3rem;
		display: flex;
		flex-direction: row;
		height: 100%;
	}

	.content {
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 1rem;
		width: 100%;
		height: 100%;
		overflow-y: auto;
		align-items: start;
	}

	.content-inner {
		width: 80ch;
	}
</style>
