<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :swiperList="swiperList"></home-swiper>
    <home-icons :iconList="iconList"></home-icons>
    <home-recommend :recommendList="recommendList"></home-recommend>
  </div>
</template>
<script>
import HomeHeader from './subcomponents/Header'
import HomeSwiper from './subcomponents/Swiper'
import HomeIcons from './subcomponents/Icons'
import HomeRecommend from './subcomponents/Recommend'
import axios from 'axios'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: []
    }
  },
  created () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/api/index.json')
        .then(res => {
          if (res.data.ret) {
            var data = res.data.data
            this.city = data.city
            this.swiperList = data.swiperList
            this.iconList = data.iconList
            this.recommendList = data.recommendList
          }
        })
    }
  }
}
</script>
<style lang="less" scoped>
</style>
