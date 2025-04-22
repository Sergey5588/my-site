

<script>
	import CanvasDrawer from '$lib/CanvasDrawer.svelte';
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
	<button onclick={window.open(`https://github.com/${i.author}/${i.name}`)}>{i.language}</button>
{/each}


