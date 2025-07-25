<script lang="ts">
	import '@fontsource-variable/manrope';
	import '@fontsource-variable/geist-mono';

	const { children } = $props();
</script>

{@render children?.()}

<style lang="scss">
	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		all: unset;
		font-family: 'Manrope Variable', sans-serif;
		color: var(--text);
		background: var(--background);
		// https://coolors.co/palette/464545-2f2f2f-1b1b1b-f54703-ff7518
		--background: #1b1b1b;
		--background-alt: #2f2f2f;
		--background-alt-50: color-mix(in srgb, var(--background-alt), transparent);

		--text: #fcfcfc;
		--text-25: color-mix(in srgb, 25% var(--text), 75% transparent);

		--primary: #f54703;
		--primary-25: color-mix(in srgb, 25% var(--primary), 75% transparent);

		--secondary: #ff7518;
		--secondary-25: color-mix(in srgb, 25% var(--secondary), 75% transparent);

		--gold: #fcba03;
		--gold-75: color-mix(in srgb, 75% var(--gold), 25% transparent);
		--gold-50: color-mix(in srgb, 50% var(--gold), 50% transparent);
		--gold-25: color-mix(in srgb, 25% var(--gold), 75% transparent);

		--font-mono: 'Geist Mono Variable', monospace;

		--green: #4ae85f;
		--red: #ee4949;
	}
</style>
