<script lang="ts">
	import PlayIcon from './PlayIcon.svelte';

	const {
		responseType,
		route
	}: {
		responseType: 'GET';
		route: string;
	} = $props();

	let showingResponse = $state(false);
</script>

<div class="wrap">
	<span class="top">
		<button class="play" onclick={() => (showingResponse = !showingResponse)}
			><span class:showing={showingResponse} class="iconSpan"><PlayIcon /></span></button
		>
		<p class="command">
			<span class="curlCommand">curl -X {responseType} </span>
			<span class="route">"{route}"</span>
		</p>
	</span>

	<div class="res" class:showing={showingResponse}>
		<img src={route} alt="Example" />
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
		justify-content: start;
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

	.command {
		margin: 0;
		word-wrap: break-word;
		word-break: break-all;
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
		display: flex;
		align-items: center;
		justify-content: center;
		transition: height 0.25s cubic-bezier(0.455, 0.03, 0.515, 0.955);

		img {
			height: 100%;
			padding: 1rem;
			aspect-ratio: 1/1;
		}

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
