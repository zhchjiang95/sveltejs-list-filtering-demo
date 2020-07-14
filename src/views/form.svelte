<script>
  // 接收props传入并设置默认值
  export let handleSubmit = function(e){
    console.log('submit')
  }
</script>
<!-- 响应事件及添加事件修饰符 -->
<form on:submit|preventDefault={handleSubmit}>
  <label for="search">search</label>
  <input type="search" placeholder="p ipunt..." id="search" value="A" />
  <button type="submit">search</button>
</form>