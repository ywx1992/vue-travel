<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <h3 class="title">当前位置</h3>
        <div class="position">
          北京
        </div>
      </div>
      <div class="area">
        <h3 class="title">热门城市</h3>
        <div class="city-list">
          <ul>
            <li class="border-rightbottom">北京</li>
            <li class="border-rightbottom">上海</li>
            <li class="border-rightbottom">广州</li>
            <li class="border-rightbottom">深圳</li>
            <li class="border-rightbottom">香港</li>
            <li class="border-rightbottom">天津</li>
            <li class="border-rightbottom">重庆</li>
            <li class="border-rightbottom">南京</li>
          </ul>
        </div>
      </div>
      <div class="area">
        <h3 class="title">A</h3>
        <div class="character-list">
          <ul>
            <li class="border-rightbottom">北京</li>
            <li class="border-rightbottom">香港特别行政区</li>
            <li class="border-rightbottom">广州</li>
            <li class="border-rightbottom">深圳</li>
            <li class="border-rightbottom">广西壮族自治区</li>
            <li class="border-rightbottom">天津</li>
            <li class="border-rightbottom">重庆</li>
            <li class="border-rightbottom">南京</li>
          </ul>
        </div>
      </div>
      <div class="area">
        <h3 class="title">B</h3>
        <div class="character-list">
          <ul>
            <li class="border-rightbottom">北京</li>
            <li class="border-rightbottom">香港特别行政区</li>
            <li class="border-rightbottom">广州</li>
            <li class="border-rightbottom">深圳</li>
            <li class="border-rightbottom">广西壮族自治区</li>
            <li class="border-rightbottom">天津</li>
            <li class="border-rightbottom">重庆</li>
            <li class="border-rightbottom">南京</li>
          </ul>
        </div>
      </div>
      <div class="area">
        <h3 class="title">C</h3>
        <div class="character-list">
          <ul>
            <li class="border-rightbottom">北京</li>
            <li class="border-rightbottom">香港特别行政区</li>
            <li class="border-rightbottom">广州</li>
            <li class="border-rightbottom">深圳</li>
            <li class="border-rightbottom">广西壮族自治区</li>
            <li class="border-rightbottom">天津</li>
            <li class="border-rightbottom">重庆</li>
            <li class="border-rightbottom">南京</li>
          </ul>
        </div>
      </div>
      <div class="area">
        <h3 class="title">D</h3>
        <div class="character-list">
          <ul>
            <li class="border-rightbottom">北京</li>
            <li class="border-rightbottom">香港特别行政区</li>
            <li class="border-rightbottom">广州</li>
            <li class="border-rightbottom">深圳</li>
            <li class="border-rightbottom">广西壮族自治区</li>
            <li class="border-rightbottom">天津</li>
            <li class="border-rightbottom">重庆</li>
            <li class="border-rightbottom">南京</li>
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
      .position{
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
