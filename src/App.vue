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


{
  "name": "mps",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  },
  "dependencies": {
    "axios": "^0.19.2",
    "core-js": "^3.6.5",
    "hikui": "^0.1.31",
    "lodash": "^4.17.19",
    "normalize.css": "^8.0.1",
    "vue": "^2.6.11",
    "vue-i18n": "^8.15.5",
    "vue-rate": "^2.4.0",
    "vue-router": "^3.2.0",
    "vuex": "^3.4.0"
  },
  "devDependencies": {
    "@vue/cli-plugin-babel": "^4.4.0",
    "@vue/cli-plugin-eslint": "^4.4.0",
    "@vue/cli-service": "^4.4.0",
    "@vue/eslint-config-standard": "^5.1.2",
    "babel-eslint": "^10.1.0",
    "eslint": "^6.7.2",
    "eslint-plugin-import": "^2.20.2",
    "eslint-plugin-node": "^11.1.0",
    "eslint-plugin-promise": "^4.2.1",
    "eslint-plugin-standard": "^4.0.0",
    "eslint-plugin-vue": "^6.2.2",
    "node-sass": "^4.12.0",
    "sass-loader": "^8.0.2",
    "vue-template-compiler": "^2.6.11"
  }
}
