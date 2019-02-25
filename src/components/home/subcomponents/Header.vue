<template>
  <div class="header">
    <div class="header-left">
      <i class="iconfont iconfanhui"></i>
    </div>
    <div class="header-input">
      <i class="iconfont iconsousuo"></i>
      <span>输入城市、景点、游玩主题</span>
    </div>
    <router-link to="/city">
    <div class="header-right">
      <span>{{city}}</span>
      <i class="iconfont iconjiantou"></i>
    </div>
    </router-link>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  computed: {
    city () {
      return this.$store.state.city.substring(0, 4)
    }
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  .header {
    display: flex;
    height: @headerHeight;
    line-height: @headerHeight;
    background-color: @bgColor;
    color: #fff;
    .header-left {
      width: 0.7rem;
      text-align: center;
    }
    .header-input {
      flex: 1;
      height: 0.6rem;
      line-height: 0.6rem;
      margin-top: 0.13rem;
      margin-left: 0.15rem;
      padding-left: 0.1rem;
      border-radius: 0.08rem;
      background-color: #fff;
      color: #ccc;
    }
    .header-right {
      min-width: 1rem;
      padding:0 0.2rem;
      text-align: center;
      color: #fff;
      .iconjiantou {
        font-size: 0.24rem;
        margin-left: -0.05rem;
      }
    }
  }
</style>
