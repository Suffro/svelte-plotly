<script>
import TestPlot from "../components/testPlot.svelte";
import TestTable from "../components/testTable.svelte";
import { testDataPlot, testDataTable } from "../stores/store";

let plotOutputObj = JSON.parse(testDataPlot);

let tableOutputObj = JSON.parse(testDataTable);

let arr = [1,2];

</script>

<div class="grid grid-cols-2 gap-4">
    {#each arr as item, i}  
        <div class="">
            <TestPlot key={i} data={plotOutputObj.output[0].outputData.data} layout={plotOutputObj.output[0].outputData.layout}/>
        </div>
    {/each}
</div>
<div style="margin-bottom: 100px;">
    <TestTable data={tableOutputObj}/>
</div>