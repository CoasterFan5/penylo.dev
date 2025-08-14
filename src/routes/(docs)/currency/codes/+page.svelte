<script>
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>currency.penylo.dev/codes</h2>
<p>This route is used to get a list of all currency codes that are supported.</p>

<h3>Example:</h3>
<TryQuery responseType="GET" route="https://currency.penylo.dev/codes/" />
