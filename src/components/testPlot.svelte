<script>
	import { onMount } from 'svelte';

	let headerText;

    export let id;

	export let plotHeader = '';

	export let data = [
		{
			x: ['giraffes', 'orangutans', 'monkeys'],
			y: [20, 14, 23, 20],
			type: 'bar'
		}
	];

    export let layout = {
        title: 'Test Plot'
    };

	onMount(() => {
		headerText = 'OnMount called';
		let plotDiv = document.getElementById('plotDiv'+id);
		new Plotly.newPlot(plotDiv, data, layout, { showSendToCloud: true, editable: true });
	});
</script>

<svelte:head>
	<script src="https://cdn.plot.ly/plotly-latest.min.js" type="text/javascript"></script>
</svelte:head>

<small>{headerText}</small>
<div id="plotly">
	<div>
		<h1>{plotHeader}</h1>
	</div>
	<div id={`plotDiv${id}`} class="plot-container"><!-- Plotly chart will be drawn inside this DIV --></div>
</div>

<style>
    .plot-container{
        height: 500px;
    }
</style>