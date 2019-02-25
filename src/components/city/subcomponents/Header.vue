<template>
  <div class="header-wrapper">
    <div class="header">
      城市选择
      <router-link to="/">
      <i class="iconfont iconfanhui"></i>
      </router-link>
    </div>
    <div class="region">
      <ul>
        <router-link to="#">
          <li
            v-for="(item, index) in region"
            :key="index"
            :class="{active:selected==index}"
            @click="change(index)"
          >{{item}}</li>
        </router-link>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      region: ['境内', '境外·港澳台'],
      selected: 0
    }
  },
  methods: {
    change (index) {
      this.selected = index
    }
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  .header{
    height: @headerHeight;
    line-height: @headerHeight;
    text-align: center;
    background-color: @bgColor;
    color: #fff;
    font-size: 0.32rem;
    position: relative;
    .iconfanhui{
      position: absolute;
      top: 0;
      left: 0.19rem;
      color: #fff;
    }
  }
  .region{
    height: 0.8rem;
    background-color: @bgColor;
    overflow: hidden;
    ul{
      width: 5.46rem;
      height: 0.4rem;
      margin: 0 auto;
      margin-top: 0.2rem;
      border: 1px solid #fff;
      li{
        float: left;
        width: 50%;
        text-align: center;
        line-height: 0.4rem;
        color: #fff;
        &.active {
          background-color: #fff;
          color: @bgColor;
        }
      }
    }
  }
</style>
