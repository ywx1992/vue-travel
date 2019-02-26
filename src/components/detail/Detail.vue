<template>
  <div class="detail">
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :categoryList="categoryList"></detail-list>
    </div>
  </div>
</template>
<script>
import DetailBanner from './subcomponents/Banner'
import DetailHeader from './subcomponents/Header'
import DetailList from './subcomponents/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  created () {
    this.getDetailInfo()
  },
  activated () {
    this.getDetailInfo()
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: {id: this.$route.params.id}
      })
        .then(res => {
          if (res.data.ret) {
            var data = res.data.data
            this.sightName = data.sightName
            this.bannerImg = data.bannerImg
            this.gallaryImgs = data.gallaryImgs
            this.categoryList = data.categoryList
          }
        })
    }
  }
}
</script>
<style>
  .content{
    height: 20rem;
  }
</style>
