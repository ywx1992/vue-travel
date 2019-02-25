<template>
  <div class="banner-wrapper">
    <div class="banner" @click="handleBannerClick">
      <img src="//img1.qunarzz.com/sight/p0/1603/9b/9bf694a468dd774490.water.jpg_600x330_208523f8.jpg" alt="" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">上海欢乐谷(AAA景区)</div>
        <div class="banner-number">
          <i class="iconfont icontukuxiangce"></i>
          538
        </div>
      </div>
    </div>
    <common-gallary
      :images="images"
      v-show="showGallary"
      @handleGallaryClose="handleGallaryClose"
    ></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  data () {
    return {
      images: ['http://img1.qunarzz.com/sight/p0/1802/d3/d345e53fdc97849ba3.img.jpg_r_800x800_409661da.jpg',
        'http://img1.qunarzz.com/sight/p0/1802/63/6313bacc3badf04ba3.img.jpg_r_800x800_55645399.jpg'],
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
}
</script>
<style lang="less" scoped>
  .banner {
    &::after{
      content: '';
      display: block;
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      min-height: 0.6rem;
      background-image: linear-gradient(to bottom, rgba(0,0,0,0), rgba(0,0,0,0.6));
    }
      position: relative;
      overflow: hidden;
      height: 0;
      padding-bottom: 55%;

      .banner-img {
        width: 100%;
      }

      .banner-info {
        position: absolute;
        bottom: 0.3rem;
        left: 0.2rem;
        right: 0.2rem;
        display: flex;
        justify-content: space-between;
        color: #fff;
        .banner-title {
          font-size: .32rem;
          height: 0.4rem;
          line-height: 0.4rem;
        }

        .banner-number {
          width: .9rem;
          height: .4rem;
          line-height: 0.4rem;
          background-color: rgba(0, 0, 0, .5);
          padding: 0 .2rem;
          border-radius: .2rem;
          text-align: center;
          font-size: .24rem;

          .icontukuxiangce {
            font-size: .28rem;
          }
        }
      }
    }
</style>
