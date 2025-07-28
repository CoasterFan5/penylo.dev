<script lang="ts">
	let {
		overlaySidebar = false
	}: {
		overlaySidebar: boolean;
	} = $props();
</script>

<div class="sidebar" class:overlay={overlaySidebar}>
	<div class="section">
		<span class="sectionHead">Hello Penylo</span>
		<a class="pageLink" href="/">About</a>
		<a class="pageLink" href="/pricing">Pricing</a>
		<a class="pageLink" href="/auth">Auth</a>
	</div>

	<div class="section">
		<span class="sectionHead">/currency</span>
		<a class="pageLink" href="/currency">/</a>
		<a class="pageLink" href="/currency/codes">/codes</a>
		<a class="pageLink" href="/currency/rates">/rates/::</a>
	</div>
</div>

<style lang="scss">
	.sidebar {
		padding: 1rem 0;
		border-right: 1px solid var(--text-25);
		display: flex;
		flex-direction: column;
		min-width: 13rem;
		font-family: var(--font-mono);
		height: 100%;
		padding: 1rem 1rem;
		background: var(--background);
	}

	.section {
		margin-bottom: 1rem;
		font-size: 1rem;
		display: flex;
		flex-direction: column;
	}

	.pageLink {
		padding: 0.1rem;
		padding-left: 0.5rem;
		border-left: 1px solid var(--text-25);
		cursor: pointer;
		color: var(--text);
		text-decoration: none;

		&:hover {
			color: var(--primary);
		}
	}

	.sectionHead {
		display: flex;
		font-weight: 700;
		margin: 0;
		text-decoration: underline;
	}

	.overlay {
		position: absolute;
		z-index: 100;
		height: calc(100dvh);
	}
</style>
