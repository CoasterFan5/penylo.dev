<script>
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>/v1/</h2>

<p>NOTICE: Penylo will start enforcing versioning on this route August 31st.</p>

<p>
	If you want a list of all SEC recognized tickers, you can use this api route. Note, it caps the
	returned tickers at 100
</p>

<TryQuery responseType="GET" route="https://tickers.penylo.dev/v1/" />

<p>You can use query parameters to search for a specific string.</p>
<TryQuery responseType="GET" route="https://tickers.penylo.dev/v1/?q=Apple" />

<p>
	If you need to get more results from the query, you can use the skip header to skip x amount of
	results. Note: The total records field does not change when using skip.
</p>

<TryQuery responseType="GET" route="https://tickers.penylo.dev/v1/?q=Apple&skip=2" />
