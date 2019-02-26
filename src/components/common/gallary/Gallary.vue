<template>
  <div class="gallary" @click="handleGallaryClick">
    <div class="container">
      <div class="swiper">
        <swiper :options="swiperOption">
          <!-- slides -->
          <swiper-slide v-for="(item, index) in gallaryImgs" :key="index">
            <img class="gallary-img" :src="item" alt="">
          </swiper-slide>
          <!-- Optional controls -->
          <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  props: {
    gallaryImgs: Array
  },
  methods: {
    handleGallaryClick () {
      this.$emit('handleGallaryClose')
    }
  }
}
</script>
<style lang="less" scoped>
  .gallary {
    z-index: 99;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    background-color: #000;
    display: flex;
    flex-direction: column;
    justify-content: center;
    .container{
      /*overflow: hidden;*/
      height: 0;
      padding-bottom: 100%;
      .gallary-img{
        width: 100%;
      }
      .swiper-container{
        overflow: inherit;
        .swiper-pagination{
          bottom: -2rem;
          color: #fff;
          z-index: 100;
        }
      }
    }
  }
</style>
