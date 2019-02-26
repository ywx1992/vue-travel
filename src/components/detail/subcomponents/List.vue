<template>
  <div class="list">
    <div class="ticket">
      <div v-for="(item, index) in categoryList" :key="index">
        <div class="ticket-title border-bottom">
          <span class="ticket-img"></span>
          {{item.title}}
        </div>
        <div v-if="item.children" class="ticket-children">
          <detail-list :categoryList="item.children"></detail-list>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailList',
  props: {
    categoryList: Array
  }
}
</script>
<style lang="less" scoped>
  .ticket{
    .ticket-title{
      height: 1rem;
      line-height: 1rem;
      border-color: #333;
      .ticket-img{
        display: inline-block;
        position: relative;
        width: .36rem;
        height: .36rem;
        top: .1rem;
        left: .2rem;
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat;
        margin-right: .2rem;
        background-size: .4rem 3rem;
      }
    }
    .ticket-children{
      padding-left: 0.6rem;
      color: #666;
    }
  }
</style>
