<script>
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>icons.penylo.dev/list.json</h2>

<p>This route returns a list of all supported logo keys.</p>

<TryQuery responseType="GET" route="https://icons.penylo.dev/list.json" />
