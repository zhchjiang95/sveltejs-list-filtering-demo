<script>
  // 导入生命周期钩子
  import { onMount } from 'svelte'
  export let searchTerm = undefined
  const abc = ['A', 'B', 'C', 'D', 'E']
  // $:（js原生标记），svelte'反应声明'使此段代码可响应，类似react hooks
  $: data = searchTerm ? abc.filter(v => v === searchTerm) : abc
  onMount(() => {
    console.log(searchTerm)
  })
</script>
<!-- 传递数据到父组件，=>data={data} -->
<slot {data} />