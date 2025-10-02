<script lang="ts">
	import TryQuery from '$lib/components/TryQuery.svelte';

	type SearchResult = {
		Item: {
			cik_str: number;
			ticker: string;
			title: string;
		};
		Dist: number;
	};

	let searchValue = $state('AAPL');
	let searchItemList: SearchResult[] = $state([]);

	const search = async (query: string) => {
		const fr = await fetch(`https://tickers.penylo.dev/v2/search?q=${query}`);
		return (await fr.json()) as SearchResult[];
	};

	$effect(() => {
		search(searchValue).then((v) => {
			searchItemList = v;
		});
	});
</script>

<h2>tickers.penylo.dev/v2/search</h2>

<p>With Penylo Tickers v2, searching has been improved.</p>
<TryQuery responseType="GET" route="https://tickers.penylo.dev/v2/search?q=AAPL" />

<p>You can either search a company name or symbol.</p>
<TryQuery responseType="GET" route="https://tickers.penylo.dev/v2/search?q=Apple In" />

<p>A great use of this API is to make searchable lists:</p>

<div class="searchableEquityList">
	<input placeholder="Search..." bind:value={searchValue} />
	<div class="list">
		{#each searchItemList as item (item.Item.ticker)}
			{#if item}
				<div class="equityCard">
					<div class="img">
						<img
							src="https://icons.penylo.dev/{item.Item.ticker}"
							alt=""
							onerror={(e) => {
								e.currentTarget.remove();
							}}
						/>
					</div>
					<div class="text">
						<span class="symbol">{item.Item.ticker}</span>
						<span class="title">{item.Item.title}</span>
					</div>
				</div>
			{/if}
		{/each}
	</div>
</div>

<p>Using search is a little slower than using the v1 API for now. It's being worked on.</p>

<style lang="scss">
	.searchableEquityList {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		input {
			background: var(--background-alt-50);
			border: 1px solid var(--background-alt);
			color: var(--text);
			padding: 0.25rem;
			font-size: 1rem;
			width: 100%;
			border-radius: 0.25rem;
		}
	}

	.list {
		background: var(--background-alt-50);
		border: 1px solid var(--background-alt);
		padding: 0.25rem;
		font-size: 1rem;
		width: 100%;
		border-radius: 0.25rem;
		display: flex;
		flex-direction: column;
		max-height: 20rem;
		overflow-y: auto;
	}

	.equityCard {
		display: flex;
		flex-direction: row;
		gap: 0.5rem;
		margin-bottom: 0.5rem;

		.img {
			border-radius: 10rem;
			height: 2.2rem;
			aspect-ratio: 1/1;
			background: black;
			overflow: hidden;

			img {
				height: 100%;
				width: 100%;
			}
		}

		.text {
			display: flex;
			flex-direction: column;
			align-items: start;
			justify-content: center;
			height: 2.2rem;

			.symbol {
				font-size: 0.8rem;
			}

			.title {
				font-size: 0.7rem;
				opacity: 0.8;
			}
		}
	}
</style>
