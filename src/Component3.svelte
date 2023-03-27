<script>
  // Please build a dynamic table component, based on the design provided plus an action column.
  // Bilal: the dynamic, reusable table is using three customizable colors, column headers and row data passed from the calling component.
  // handleClick passes rowIndex to the action method call, so that the calling component can implement row-specific logic.
  export let bgColor1, bgColor2, headerColor, columnHeaders, rows, handleClick;  
  
</script>

<style>
table {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%; 
  font-size: 30px;
  margin: 10px;
  padding: 20px;  
}
table tr {
  border: 1px solid #ddd;
  padding: 8px;
  background-color: var(--bgColor2, "#D6D6D6");
}

table th {
  background-color: var(--headerColor, "#E0E0E0");
  padding-top: 12px;
  padding-bottom: 12px;
}

table td {  
  padding-top: 12px;
  padding-bottom: 12px;
}

table tr:nth-child(even){background-color: var(--bgColor1, "#EEEEEE");}

table tr:hover {background-color: #BDBDBD;}



button {
		background: #E2E8F0;
		color: #64748B;
		border: unset;
		border-radius: 6px;
		padding: .75rem 1.5rem;
		cursor: pointer;
}
button:hover {
		background: #CBD5E1;
		color: #475569;
}
button:focus {
		background: #94A3B8;
		color: #F1F5F9;
}
</style>

<h1>Table</h1>

  <table>
    <thead>
      <tr>  
        {#each columnHeaders as column, index}
           <th scope="column">{column}</th>
        {/each}
        <th scope="column">Action</th>
      </tr>
    </thead>
    <tbody>
      {#each rows as row, rowIndex}
        <tr>
	      {#each row as cell, cellIndex}
	        <td>{cell}</td>
	      {/each}
		  <td><button on:click={handleClick(rowIndex)}>Click for action</button></td>
	    </tr>
      {/each}
	</tbody>
  </table>
