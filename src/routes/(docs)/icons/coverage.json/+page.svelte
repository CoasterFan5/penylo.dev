<script lang="ts">
	type IconCoverageBody = { count: number; percent: number; details: Record<string, boolean> };
	const fetchIconCoverage = async () => {
		const iconRequest = await fetch('https://icons.penylo.dev/coverage.json');
		return (await iconRequest.json()) as IconCoverageBody;
	};
</script>

<h2>Penylo Icons Coverage</h2>
{#await fetchIconCoverage()}
	<p>Loading Coverage Data...</p>
{:then iconCoverage}
	<p>Serving {iconCoverage.count} icons</p>
	<p>Covering {(iconCoverage.percent * 100).toFixed(2)}% of the S&P 500.</p>
{/await}
