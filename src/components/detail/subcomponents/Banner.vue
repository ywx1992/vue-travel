<template>
  <div class="banner-wrapper">
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" alt="" class="banner-img">
      <div class="banner-info">
        <div class="banner-title">{{sightName}}</div>
        <div class="banner-number">
          <i class="iconfont icontukuxiangce"></i>
          {{gallaryImgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary
        :gallaryImgs="gallaryImgs"
        v-show="showGallary"
        @handleGallaryClose="handleGallaryClose"
      ></common-gallary>
    </fade-animation>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fadeanimation/FadeAnimation'
export default {
  data () {
    return {
      showGallary: false
    }
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
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
    CommonGallary,
    FadeAnimation
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
