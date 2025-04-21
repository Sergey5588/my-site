



<style global>
	:global {
			* {
			font-family: "Inter", sans-serif !important;
		}
		
		:root {
			--bg-color: #121619;
			--font-color: #F7FFF6;
			--first-color: #63C132;
			--second-color: #19310D;
			--third-color: #DEF3D2;
		}
		
		body {
			
			background-color: var(--bg-color);
			color: var(--font-color);
		}




		button {
			padding: 10px 20px;
			font-size: 16px;
			background-color: var(--first-color);
			color: var(--font-color);
			border: none;
			border-radius: 8px;
			transition: transform 0.2s ease, box-shadow 0.2s ease;
			cursor: pointer;
		}

		/* Увеличение при hover */
		button:hover {
			transform: scale(1.1);
			box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
		}

		/* Уменьшение при нажатии */
		button:active {
			transform: scale(0.95);
		}
	}
	
	

</style>



<script>
	import CanvasDrawer from '../lib/CanvasDrawer.svelte';
	let numbers = $state([1, 2, 3, 4]);
	let total = $derived(numbers.reduce((t, n) => t + n, 0));
	let items = $state([1,2,3]);
	let pinned = $state();
	function addNumber() {
		numbers.push(numbers.length + 1);
		
		items.push(items.length+1);
	}

	async function get_repo() {
		const url = "https://pinned.berrysauce.dev/get/sergey5588";
		fetch(url).then(response=>response.json()).then(data=>pinned=data);
	}
</script>


<h1>{numbers.join(' + ')} = {total}</h1>

<button onclick={addNumber}>
	Add a number<br>hi 123
</button>
<br>
<br>
<button onclick={get_repo}>
	Get repo
</button>

{#each pinned as i}
	<h1>{i.name}</h1>
	<button>{i.language}</button>
{/each}




