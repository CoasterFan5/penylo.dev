<script lang="ts">
	import type { Snippet } from 'svelte';

	const {
		href,
		children
	}: {
		href: string;
		children: Snippet;
	} = $props();
</script>

<a {href}>
	{@render children?.()}
</a>

<style lang="scss">
	a {
		text-decoration: none;
		color: var(--primary);
		position: relative;

		&::after {
			content: '';
			position: absolute;
			left: 0px;
			bottom: 0px;
			width: 100%;
			height: 1px;
			transform: scaleX(0);
			background: var(--primary);
			transition: all cubic-bezier(0.455, 0.03, 0.515, 0.955) 0.25s;
		}

		&:hover {
			&::after {
				transform: scaleX(1);
			}
		}
	}
</style>
