<script>
	
	let name = 'svelte';
	let data = new Array(500)
	function click(index){
		return ()=>{
			data[index] = 'test'
		}
	}
</script>

<div>数据量: { data.length }</div>
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