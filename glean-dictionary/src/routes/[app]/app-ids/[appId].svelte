<script context="module">
	export async function load({ page, fetch }) {
		const metricName = page.params.appId.replace(/\./g, '_');
		const res = await fetch(`/data/${page.params.app}/app_ids/${metricName}.json`);
		const metric = await res.json();
		console.log(metric);

		return {
			props: { metric }
		};
	}
</script>

<script>
	export let metric;
</script>

<h1>{metric.app_id}</h1>
