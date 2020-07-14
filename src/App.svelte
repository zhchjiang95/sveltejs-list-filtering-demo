<script>
	import Fetch from './views/fetch.svelte';
	import Form from './views/form.svelte'
	export let name = 'fiume.cn'
	let searchTerm
	let handleSubmit = function(){
		searchTerm = this.elements.search.value
	}
</script>

<main>
	<!-- 传递props，=>handleSubmit={handleSubmit} -->
	<Form {handleSubmit} />
		<!-- 插槽slot方式，接收子组件传来的data，=>let:data={data} -->
	<Fetch {searchTerm} let:data>
		<h1>{name}</h1>
		<!-- 循环 -->
		{#each data as item, i}
			<ul>
				<li>{++i} - {item}</li>
			</ul>
		{/each}
	</Fetch>
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