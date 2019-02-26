<template>
  <div class="header">
    <router-link to="/" tag="div" class="goBack" v-show="flag">
      <i class="iconfont iconfanhui"></i>
    </router-link>
    <div class="header-fixed" v-show="!flag" :style="opacityStyle">
        上海欢乐谷(AAA景点)
        <router-link to="/">
          <i class="iconfont iconfanhui"></i>
        </router-link>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      flag: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll (e) {
      const top = e.target.scrollingElement.scrollTop
      // console.log(top)
      if (top > 46) {
        let opacity = top / 200
        opacity = opacity >= 1 ? 1 : opacity
        this.opacityStyle = {opacity}
        this.flag = false
      } else {
        this.flag = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables";
  .header{
    .goBack {
      position: absolute;
      top: 0.2rem;
      left: 0.2rem;
      width: 0.72rem;
      height: .72rem;
      line-height: 0.72rem;
      border-radius: 50%;
      background-color: rgba(0, 0, 0, .4);
      color: #fff;
      text-align: center;
    }
    .header-fixed{
      z-index: 99;
      height: @headerHeight;
      line-height: @headerHeight;
      text-align: center;
      background-color: @bgColor;
      color: #fff;
      font-size: 0.32rem;
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      .iconfanhui{
        position: absolute;
        top: 0;
        left: 0.19rem;
        color: #fff;
      }
    }
  }
</style>
