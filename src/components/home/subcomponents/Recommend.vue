<template>
  <div class="recommend">
    <div class="recommend-title border-bottom">猜你喜欢</div>
    <ul>
      <li class="recommend-item border-bottom"
          v-for="item in recommendList"
          :key="item.id">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="item-content">
          <p class="title">{{item.title}}</p>
          <p class="desc">{{item.desc}}</p>
          <p class="price">&yen;<span>{{item.price}}</span> 起</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  data () {
    return {
    }
  },
  props: {
    recommendList: Array
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  @import "~@/assets/styles/mixins.less";
  .recommend-title {
    height: 0.96rem;
    font-size: 0.32rem;
    color: @textColor;
    line-height: 0.96rem;
    text-indent: 1em;
    /*margin-top: 0.2rem;*/
    border-top: 0.2rem solid #eee;
  }
  .recommend-item {
    display: flex;
    height: 2.4rem;
    margin-left: 0.2rem;
    .item-img {
      width: 2rem;
      height: 2rem;
      padding: 0.2rem 0;
    }
    .item-content {
      font-size: 0.24rem;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      padding: 0.4rem 0 0.4rem 0.2rem;
      min-width: 0;
      .title {
        font-size: 0.32rem;
      }
      .desc {
        color: #616161;
        .ellipsis();
      }
      .price {
        span {
          font-size: 0.32rem;
          color: @priceColor;
        }
      }
    }
  }
</style>
