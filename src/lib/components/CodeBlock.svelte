<script lang="ts">
	const {
		code,
		language = 'bash'
	}: {
		code: string;
		language: string;
	} = $props();

	const getCodeHighlighter = async () => {
		const highlighter = await createHighlighter({
			langs: ['html', 'typescript', 'bash', 'json'],
			themes: ['github-dark', 'github-light']
		});
		await highlighter.loadTheme('vesper');
		return highlighter;
	};

	import { createHighlighter } from 'shiki/bundle/web';
</script>

{#await getCodeHighlighter() then high}
	<div class="codeBlockWrap">
		<!-- eslint-disable-next-line -->
		{@html high.codeToHtml(code, {
			lang: language,
			theme: 'vesper'
		})}
	</div>
{/await}

<style lang="scss">
	:global(.codeBlockWrap > pre) {
		border-radius: 0.5rem;
		padding: 1rem;
	}

	code {
		background: var(--primary-10);
		padding: 1rem;
		border: 1px solid var(--text-25);
		display: flex;
		border-radius: 0.5rem;
	}
</style>
