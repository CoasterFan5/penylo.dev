<script>
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>/v2/</h2>

<p>NOTICE: This route is marked as experimental.</p>

<p>With Penylo Tickers v2, we have made searching available.</p>
<TryQuery responseType="GET" route="https://tickers.penylo.dev/v2/search?q=AAPL" />

<p>Using search is a little slower than using the v1 API for now. It's being worked on.</p>
