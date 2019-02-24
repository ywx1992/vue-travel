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
      recommendList: [
        {id: '001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1611/66/66d2a3f686830d2ea3.water.jpg_200x200_3e56a6cb.jpg',
          title: '水之星豪华游轮',
          desc: '阻力非常小，稳定性极佳， 适航性更强。很好的很好奥斯卡卢卡申科拉克丝拉卡拉',
          price: 398
        }, {id: '002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1805/74/748061410bd7d7a0a3.img.jpg_200x200_5c405a91.jpg',
          title: '卡乐星球',
          desc: '“科技版欢乐谷”，育智于乐',
          price: 398
        }, {id: '003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1808/47/4766ee01cea6f21aa3.water.jpg_200x200_e2a8e8ee.jpg',
          title: '水之星豪华游轮',
          desc: '阻力非常小，稳定性极佳， 适航性更强',
          price: 398
        }
      ]
    }
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
    margin-top: 0.2rem;
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
