<script context="module">
	export async function load({ page, fetch }) {
		const res = await fetch(`/data/${page.params.app}/pings/${page.params.ping}.json`);
		const ping = await res.json();
		console.log(page.params);

		return {
			props: { ping }
		};
	}
</script>

<script>
	export let ping;
</script>

<h1>{ping.name}: {ping.description}</h1>
