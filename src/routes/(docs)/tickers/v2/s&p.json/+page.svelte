<script>
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>tickers.penylo.dev/v2/s&p.json</h2>

<p>Get the symbol of the ~500 items that make up the S&P 500.</p>
<TryQuery responseType="GET" route="https://tickers.penylo.dev/v2/s&p.json" />
