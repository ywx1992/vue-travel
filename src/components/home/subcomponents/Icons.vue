<template>
  <div class="wrapper">
    <div class="icons">
      <ul class="icon-list">
        <li class="icon-content" v-for="item in iconList" :key="item.id">
          <img :src="item.imgUrl" alt="">
          <p>{{item.desc}}</p>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
    }
  },
  props: {
    iconList: Array
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  .icons {
    height: 3.41rem;
    /*background-color: blue;*/
    .icon-content {
      float: left;
      width: 25%;
      height: 25%;
      text-align: center;
      padding-top: 0.2rem;
      img {
        width: 60%;
      }
      p {
        color: @textColor;
        font-size: 0.28rem;
        padding-top: 0.1rem;
      }
    }
  }
</style>
