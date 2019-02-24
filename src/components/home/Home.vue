<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
  </div>
</template>
<script>
import HomeHeader from './subcomponents/Header'
import HomeSwiper from './subcomponents/Swiper'
import HomeIcons from './subcomponents/Icons'
import HomeRecommend from './subcomponents/Recommend'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  }
}
</script>
<style lang="less" scoped>
</style>
