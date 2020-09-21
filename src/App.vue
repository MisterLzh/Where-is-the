<template>
  <div id="app">
    <!-- keep-alive  当router-view里面的内容加载过一次之后就会直接保存到内存之中  不需要每次切换页面都重新请求加载数据 -->
    <keep-alive exclude="Detail">
      <router-view />
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
</style>
