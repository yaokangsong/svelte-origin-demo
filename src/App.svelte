<script>
	import { onMount } from 'svelte';
	
	const list  = []
	for(let i = 0; i < 50000; i++) {
		list.push(i);
	}
	const beginTime = +new Date();
	let name = 'world';
	let data = new Array(1000)
	function click(index){
		return ()=>{
			data[index] = 'test'
		}
	}
	onMount(()=>{
		const endTime = +new Date();
	  console.log((endTime - beginTime) / 1000,1);
	})
</script>

{#each data as d, i}
<h1 on:click={click(i)}>
	<span>
		<span>
			<span>
				<span>
					Hello {name} {i} {d}!
				</span>
			</span>
		</span>
	</span>
</h1>
{/each}