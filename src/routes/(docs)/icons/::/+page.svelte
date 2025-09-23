<script>
	import Link from '$lib/components/Link.svelte';
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>icons.penylo.dev/::</h2>

<p>
	Replace :: with any of the <Link href="/icons/list.json">supported logo keys</Link>. This route
	returns an svg for the key.
</p>

<TryQuery responseType="GET" route="https://icons.penylo.dev/aapl" />
