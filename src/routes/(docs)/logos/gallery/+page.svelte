<script lang="ts">
	import { onMount } from 'svelte';

	let items: [string, string][] = $state([]);

	onMount(async () => {
		const resp = await fetch('https://logo.penylo.dev/list.json');
		const fetchedItems = (await resp.json()).items as Record<string, string[]>;

		for (const key in fetchedItems) {
			items.push([key, fetchedItems[key][0]]);
		}
		console.log($state.snapshot(items));
	});
</script>

<h2>Penylo Logo Gallery ({items.length} items)</h2>

<div class="logos">
	{#each items as item (item[0])}
		<div class="logoGrid">
			<img loading="lazy" class="square" src="https://logo.penylo.dev/{item[1]}" alt="" />
			<img loading="lazy" class="square-2" src="https://logo.penylo.dev/{item[1]}" alt="" />
			<img loading="lazy" class="square-3" src="https://logo.penylo.dev/{item[1]}" alt="" />
			<img loading="lazy" class="circle" src="https://logo.penylo.dev/{item[1]}" alt="" />
		</div>
	{/each}
</div>

<style lang="scss">
	.logos {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(calc(6rem + 1px), 1fr));
		gap: 0.25rem;
	}

	.logoGrid {
		display: grid;
		grid-template-columns: repeat(auto-fill, minmax(3rem, 1fr));
		gap: 1px;
		img {
			width: 100%;
			height: 100%;

			&.square-2 {
				border-radius: 0.25rem;
			}

			&.square-3 {
				border-radius: 0.5rem;
			}

			&.circle {
				border-radius: 100%;
			}
		}
	}
</style>
