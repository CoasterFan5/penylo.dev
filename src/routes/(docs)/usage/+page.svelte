<script>
	import Link from '$lib/components/Link.svelte';
</script>

<h2>Usage Notice</h2>
<p>
	Unlike <Link href="/pricing">/pricing</Link> and <Link href="/auth">/auth</Link> this is a serious
	page.
</p>

<h2>Notice</h2>
<p>
	Penylo is a side project of mine that I am using to distribute financial data from a variety of
	sources to users for free. There is a long trend in the financial data space to provide very low
	usage limits for free, and then charge a large sum of money for anything more. This model is not
	great for people who just need quick data that isn't necessarily 100% accurate, but is close
	enough.
</p>

<p>
	To solve this, I created Penylo, which provides free financal data with 0 rate limits and 0
	authentication required. However, there is a cost to me to serve this financial data. <strong
		>I kindly ask that you do not make an unreasonable number of requests to the APIs in order to
		ensure this model is sustainable for everyone.</strong
	> If there is rampant abuse of Penylo APIs, I may have to add authentication and rate limits, which
	no one wants
</p>

<h2>"Reasonable Request Numbers"</h2>
<p>
	This is very simple. Take for example the <Link href="/tickers">/tickers</Link> api. If you wanted
	to implement a search box for tickers onto your page, consider adding debounce to minimize the number
	of useless requests to Penylo, while still giving users quick search updates.
</p>

<p>
	Another example, <Link href="https://github.com/CoasterFan5/currency-translator-bot"
		>Currency Translator</Link
	> fetches data from the Penylo api every 30 minutes and stores it, rather than making a new request
	when it needs exchange data.
</p>
