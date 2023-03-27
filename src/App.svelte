<script>
	import Component1 from './Component1.svelte';
	import Component2 from './Component2.svelte';
	import Component3 from './Component3.svelte';

	export let name;
	let columnHeaders = ["Name","Protocol","Port","Rule","Attached Groups","Status"];
	let rows = [
	  ["Load Balancer 3","HTTP","3000","Round robin","Kevins VM Groups","Disabled"],
	  ["Load Balancer 1","HTTP","443","Round robin","Maureens VM Groups","Starting"],
	  ["Load Balancer 2","HTTP","80","DNS delegation","Andrews VM Groups","Active"],
	  ["Load Balancer 6","HTTP","3000","Round robin","Marcs VM Groups","Disabled"],
	  ["Load Balancer 4","HTTP","443","Round robin","Mels VM Groups","Starting"],
	  ["Load Balancer 5","HTTP","80","DNS delegation","Ronjas VM Groups","Active"]
	];
	
	// Bilal: implement row-specific logic.
	 function handleClick(rowIndex) {
       alert('Action taken for row: ' + rowIndex);
     }
</script>

<main>
	<h1>Hello {name}!</h1>

	<Component1 />
	<Component2 />
	<Component3 
	   columnHeaders={columnHeaders} rows={rows}
       --bgcolor1="#EFEFEF" --bgColor2="#D9D9D9" --headerColor= "#E5E7E9"
	   handleClick={handleClick}
	/>
	<Component3 
	   columnHeaders={columnHeaders} rows={rows}
       --bgcolor1="#B2BEB5" --bgColor2="#7393B3" --headerColor= "grey"
	   handleClick={handleClick}
	/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>