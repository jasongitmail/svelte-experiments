<script context="module">
	// module runs on server only.

	// Server date and client date will be different on *first load* only
	// because serverDate will be SSR'd. After that they will match.
	// serverDate = new Date().toISOString();
	let clientDate, serverDate;

	export function preload({ params, query }) {
		clientDate = new Date().toISOString();
		serverDate = new Date().toISOString();
		return {serverDate, clientDate}
	}
</script>

<script>
	export let serverDate;
	let clientDate = new Date().toISOString();
</script>


<svelte:head>
	<title>About</title>
</svelte:head>

<h1>About this site</h1>

<p>This is the 'about' page. There's not much here.</p>
<p>Server date: {serverDate}</p>
<p>Client date: {clientDate}</p>
