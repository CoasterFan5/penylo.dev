<script lang="ts">
	import CodeBlock from './CodeBlock.svelte';
	import PlayIcon from './PlayIcon.svelte';

	const {
		responseType,
		route
	}: {
		responseType: 'GET';
		route: string;
	} = $props();

	let showingResponse = $state(false);

	const getResponse = async () => {
		const res = await fetch(route, {});
		return await res.json();
	};
</script>

<div class="wrap">
	<span class="top">
		<button class="play" onclick={() => (showingResponse = !showingResponse)}
			><span class:showing={showingResponse} class="iconSpan"><PlayIcon /></span></button
		>
		<span class="curlCommand">curl -X {responseType} </span>
		&MediumSpace;
		<span class="route">"{route}"</span>
	</span>

	<div class="res" class:showing={showingResponse}>
		{#if showingResponse}
			<hr />
			{#await getResponse() then res}
				<CodeBlock code={JSON.stringify(res, null, 4)} language="json" />
			{/await}
		{/if}
	</div>
</div>

<style lang="scss">
	.wrap {
		background: #101010;
		padding: 0.5rem;
		border-radius: 0.25rem;
		display: flex;
		flex-direction: column;
	}

	.top {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	hr {
		opacity: 0.1;
		width: 100%;
	}

	button {
		all: unset;
		color: var(--text);
		display: flex;
		align-items: center;
		justify-content: center;
		aspect-ratio: 1/1;
		height: 2ch;
		border-radius: 0.25rem;
		margin-right: 0.5rem;
		padding: 0.25rem;
		color: var(--primary);
		background: var(--primary-10);
		box-sizing: border-box;
		cursor: pointer;

		&:hover {
			color: var(--text);
			background: var(--primary);
		}
	}

	.curlCommand {
		color: #ffc799;
	}

	.route {
		color: #99ffe4;
	}

	.res {
		height: 0;
		overflow-y: auto;
		transition: height 0.25s cubic-bezier(0.455, 0.03, 0.515, 0.955);

		&.showing {
			height: 20rem;
		}
	}

	.iconSpan {
		rotate: 0;
		transition: rotate 0.25s cubic-bezier(0.455, 0.03, 0.515, 0.955);
	}

	.iconSpan.showing {
		rotate: -90deg;
	}

	@keyframes resAnimation {
		0% {
			height: 0;
		}
		100% {
			height: 20rem;
		}
	}
</style>
