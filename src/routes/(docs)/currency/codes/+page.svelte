<script>
	import CodeBlock from '$lib/components/CodeBlock.svelte';
	import Link from '$lib/components/Link.svelte';
	import { jsonResponse } from './jsonResponse';
</script>

<h2>currency.penylo.dev/codes</h2>
<p>This route is used to get a list of all currency codes that are supported.</p>

<h3>Example:</h3>
<CodeBlock code="curl https://currency.penylo.dev/codes/" language="bash" />
returns
<CodeBlock code={jsonResponse} language="json"></CodeBlock>

<h3>Important Note</h3>
<p>
	The trailing backslashes in the routes are required. <Link
		href="https://currency.penylo.dev/codes/">https://currency.penylo.dev/codes/</Link
	>
	will return the proper route, whereas
	<Link href="https://currency.penylo.dev/codes">https://currency.penylo.dev/codes</Link>
	will not.
</p>
