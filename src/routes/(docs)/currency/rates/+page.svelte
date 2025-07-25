<script>
	import CodeBlock from '$lib/components/CodeBlock.svelte';
	import Link from '$lib/components/Link.svelte';
	import { jsonResponse } from './jsonResponse';
</script>

<h2>currency.penylo.dev/rates/::</h2>
<p>Replace :: with any of the <Link href="/currency/codes/">supported currency codes</Link></p>

<h3>Example:</h3>
<CodeBlock language="bash" code="curl https://currency.penylo.dev/rates/USD"></CodeBlock>
<p>This returns the value of each currency in relation to 1 USD:</p>
<CodeBlock language="json" code={JSON.stringify(jsonResponse, null, 4)}></CodeBlock>
