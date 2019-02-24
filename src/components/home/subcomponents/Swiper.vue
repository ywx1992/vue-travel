<template>
  <div class="swiper">
    <swiper :options="swiperOption">
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
      },
      swiperList: [{
        id: '01',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20192/9f73976e40c4ef845cabe0efc0269ebb.jpg_750x200_aab92b7a.jpg'
      }, {
        id: '02',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/a211765c0bb579b18c6e7d6d75997a48.jpg_750x200_b6921fa6.jpg'
      }, {
        id: '03',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/a5379fa4391437e3c111d17e59ed24d3.jpg_750x200_3126a045.jpg'
      }]
    }
  }
}
</script>
<style lang="less" scoped>
  .swiper /deep/ .swiper-pagination-bullet-active {
    background-color: #fff !important;
  }
  .swiper {
    .swiper-img {
      width: 100%;
    }
  }
</style>
