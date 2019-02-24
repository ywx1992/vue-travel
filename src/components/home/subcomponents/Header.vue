<template>
  <div class="header">
    <div class="header-left">
      <i class="iconfont iconfanhui"></i>
    </div>
    <div class="header-input">
      <i class="iconfont iconsousuo"></i>
      <span>输入城市、景点、游玩主题</span>
    </div>
    <div class="header-right">
      <span>城市</span>
      <i class="iconfont iconjiantou"></i>
    </div>
  </div>
</template>
<script>
export default {
  // name: 'HomeHeader'
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  .header {
    display: flex;
    height: 0.86rem;
    line-height: 0.86rem;
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
      width: 1.1rem;
      padding-left: 0.2rem;
      .iconjiantou {
        font-size: 0.24rem;
        margin-left: -0.05rem;
      }
    }
  }
</style>
