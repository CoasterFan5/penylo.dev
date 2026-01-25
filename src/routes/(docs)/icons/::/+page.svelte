<script>
	import Link from '$lib/components/Link.svelte';
	import TryQueryImage from '$lib/components/TryQueryImage.svelte';
</script>

<h2>icons.penylo.dev/::</h2>

<p>
	Replace :: with any of the <Link href="/icons/list.json">supported logo keys</Link>. This route
	returns an svg for the key.
</p>

<TryQueryImage responseType="GET" route="https://icons.penylo.dev/aapl" />
