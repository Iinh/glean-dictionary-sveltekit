<script context="module">
	export async function load({ page, fetch }) {
		const metricName = page.params.metric.replace(/\./g, '_');
		const res = await fetch(`/data/${page.params.app}/metrics/${metricName}.json`);
		const metric = await res.json();
		console.log(metric, metricName);

		return {
			props: { metric }
		};
	}
</script>

<script>
	export let metric;
</script>

<h1>{metric.name}: {metric.description}</h1>
