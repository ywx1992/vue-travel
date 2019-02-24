<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons>456</home-icons>
    <div>uuuu</div>
  </div>
</template>
<script>
import HomeHeader from './subcomponents/Header'
import HomeSwiper from './subcomponents/Swiper'
import HomeIcons from './subcomponents/Icons'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>
<style>

</style>
