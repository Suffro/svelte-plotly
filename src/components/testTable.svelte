<script>
    export let data;
    let headers =  data.output[0].outputData.rows[0];
    let rows =  data.output[0].outputData.rows;
    rows.shift();
</script>


<!-- This example requires Tailwind CSS v2.0+ -->
<div class="px-4 sm:px-6 lg:px-8">
  <div class="sm:flex sm:items-center">
    <div class="sm:flex-auto">
      <h1 class="text-xl font-semibold text-gray-900">Test Table</h1>
      <!-- <p class="mt-2 text-sm text-gray-700">A list of all the users in your account including their name, title, email and role.</p> -->
    </div>
  </div>
  <div class="mt-8 flex flex-col px-6">
    <div class="-my-2 -mx-4 sm:-mx-6 lg:-mx-8">
      <div class="inline-block min-w-full align-middle qa-table border">
        <div class="shadow-sm ring-1 ring-black ring-opacity-5">
          <table class="min-w-full border-separate" style="border-spacing: 0">
            <thead class="bg-gray-50">
              <tr>
                {#each headers as item}
                    <th scope="col" class="sticky top-0 z-10 border-b border-gray-300 bg-gray-50 bg-opacity-75 py-3.5 pl-4 pr-3 text-left text-sm font-semibold text-gray-900 backdrop-blur backdrop-filter sm:pl-6 lg:pl-8">{item}</th>
                {/each}
              </tr>
            </thead>
            <tbody class="bg-white">
                {#each rows as row}
                    <tr>
                        {#each row as item}
                            <td class="whitespace-nowrap border-b border-gray-200 px-3 py-4 text-sm text-gray-500">{item}</td>  
                        {/each}
                    </tr>
                {/each}
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
    .qa-table{
        max-height: 300px;
        overflow: scroll;
    }
</style>