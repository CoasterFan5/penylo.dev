<script>
	import CodeBlock from '$lib/components/CodeBlock.svelte';
</script>

<h2>Authentication</h2>
<p>You can pass an authentication header to any Penylo API</p>

<CodeBlock
	code="curl --H &quot;Authorization: Bearer <token>&quot; <*>.penylo.dev"
	language="bash"
/>
<p>
	However, this will do nothing becase there is no authorization for any Penylo api currently. It
	might just make you more comfortable.
</p>
