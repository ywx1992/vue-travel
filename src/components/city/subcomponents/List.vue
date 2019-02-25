<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <h3 class="title">当前位置</h3>
        <div class="location">
          上海
        </div>
      </div>
      <div class="area">
        <h3 class="title">热门城市</h3>
        <div class="city-list">
          <ul>
            <li class="border-rightbottom"
            v-for="item in hotCities"
            :key="item.id">
              {{item.name}}
            </li>
          </ul>
        </div>
      </div>
      <div class="area"
           v-for="(value, key) in cities"
           :key="key"
           :ref="key"
      >
        <h3 class="title">
          {{key}}
        </h3>
        <div class="character-list">
          <ul>
            <li class="border-rightbottom"
            v-for="item in value"
            :key="item.id">
              {{item.name}}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.wrapper)
    })
  },
  watch: {
    letter () {
      if (this.letter) {
        const ele = this.$refs[this.letter][0]
        this.scroll.scrollToElement(ele)
      }
    }
  },
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/mixins.less";
  .border-rightbottom{
    &:before{
      border-color: #ccc;
    }
    &:after{
      border-color: #ccc;
    }
  }
  .list{
    overflow: hidden;
    position: absolute;
    top: 1.66rem;
    left: 0;
    right: 0;
    bottom: 0;
    .area{
      .title{
        font-size: 0.24rem;
        line-height: 0.72rem;
        background-color: #eee;
        text-indent: 1em;
      }
      .location{
        height: .9rem;
        line-height: .9rem;
        font-size: 0.32rem;
        text-indent: 1em;
      }
      .city-list{
        overflow: hidden;
        ul{
          width: 102%;
          li{
            float: left;
            width: 33.33%;
            height: .9rem;
            line-height: .9rem;
            text-align: center;
            margin-bottom: -1px;
            .ellipsis();
          }
        }
      }
      .character-list{
        overflow: hidden;
        ul{
          width: 101%;
          li{
            float: left;
            width: 25%;
            height: .9rem;
            line-height: 0.9rem;
            text-align: center;
            margin-bottom: -1px;
            .ellipsis();
          }
        }
      }
    }
  }
</style>
