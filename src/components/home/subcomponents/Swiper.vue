<template>
  <div class="swiper">
    <swiper :options="swiperOption" v-if="swiperList.length">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default{
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        autoplayDisableOnInteraction: false,
        speed: 1000,
        loop: true
      }
    }
  },
  props: {
    swiperList: Array
  }
}
</script>
<style lang="less" scoped>
  .swiper /deep/ .swiper-pagination-bullet-active {
    background-color: #fff !important;
  }
  .swiper {
    overflow: hidden;
    height: 0;
    padding-bottom: 32%;
    .swiper-img {
      width: 100%;
    }
  }
</style>
