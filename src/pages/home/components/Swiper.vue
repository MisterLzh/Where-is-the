<template>
  <div class="wrapper">
    <swiper :options="swiperOption"
            v-if="showSwiper">
      <!-- slides -->
      <swiper-slide v-for="item of list"
                    :key='item.id'>
        <img class="img-swiper"
             :src="item.imgUrl">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"
           slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    showSwiper () {
      return this.list.length
    }
  }
}
</script>
<style lang="stylus" scoped>
.wrapper>>>.swiper-pagination-bullet-active
  background #fff !important
.wrapper
  overflow hidden
  width 100%
  height 0
  padding-bottom 31.25%
  .img-swiper
    width 100%
</style>
