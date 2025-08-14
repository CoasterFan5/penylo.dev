<script>
	import Link from '$lib/components/Link.svelte';
	import TryQuery from '$lib/components/TryQuery.svelte';
</script>

<h2>currency.penylo.dev/rates/::</h2>
<p>
	Replace :: with any of the <Link href="/currency/codes/">supported currency codes</Link>. This
	route returns the rate of the currencies relative to the specified base.
</p>

<h3>Example:</h3>
<TryQuery responseType="GET" route="https://currency.penylo.dev/rates/USD" />

<h3>Example 2:</h3>
<TryQuery responseType="GET" route="https://currency.penylo.dev/rates/EUR" />
