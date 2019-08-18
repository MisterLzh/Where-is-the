<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperlist"></home-swiper>
    <home-icons :iconlist="iconlist"></home-icons>
    <home-recommend :list="recommentdlist"></home-recommend>
    <home-weektend :list="weeklist"></home-weektend>
  </div>
</template>
<script>
import { mapState } from 'vuex'
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeektend from './components/Weektend'
import axios from 'axios'
export default {
  name: 'home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeektend
  },
  data: function () {
    return {
      lastcity: '',
      swiperlist: [],
      iconlist: [],
      recommentdlist: [],
      weeklist: []
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    getHomeInfo () {
      axios.get('/static/mock/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperlist = data.swiperList
        this.iconlist = data.iconList
        this.recommentdlist = data.recommendList
        this.weeklist = data.weekendList
      }
    }
  },
  mounted () {
    this.lastcity = this.city
    this.getHomeInfo()
  },
  activated () {
    if (this.lastcity !== this.city) {
      this.lastcity = this.city
      this.getHomeInfo()
    }
  }
}
</script>
<style scoped>
</style>
