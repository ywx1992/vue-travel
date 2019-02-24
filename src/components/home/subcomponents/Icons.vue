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
      iconList: [
        {id: '01', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', desc: '景点门票'},
        {id: '02', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png', desc: '一日游'},
        {id: '03', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/48/cb72b99b71974c02.png', desc: '玩乐休闲'},
        {id: '04', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png', desc: '必游榜单'},
        {id: '05', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', desc: '景点门票'},
        {id: '06', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/50/26ffa31b56646402.png', desc: '亲子游'},
        {id: '07', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png', desc: '景点门票'},
        {id: '08', imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png', desc: '全部'}
      ]
    }
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
        font-size: 14px;
        padding-top: 0.1rem;
      }
    }
  }
</style>
