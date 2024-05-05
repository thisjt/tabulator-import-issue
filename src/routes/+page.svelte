<script>
import { TabulatorFull as Tabulator } from 'tabulator-tables';
import { onMount } from 'svelte';

onMount(() => {
  const tableTester = new Tabulator('#tabletest', {
    height: '30vh',
    layout: 'fitColumns',
    groupBy: 'group',
    columns: [
      {
        title: 'Test1',
        field: 'key',
        widthGrow: 5,
      },
      {
        title: 'Test2',
        field: 'value',
        widthGrow: 5,
      },
    ],
  });

  tableTester.on('tableBuilt', () => {
    tableTester.addData({ group: 'Test3', key: 'Test4', value: 'Test5' });
  });
});
</script>

<div id="tabletest"></div>