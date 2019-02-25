<template>
  <div class="city">
    <city-header></city-header>
    <city-list :cities="cities" :hotCities="hotCities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>
<script>
import CityHeader from './subcomponents/Header'
import CityList from './subcomponents/List'
import CityAlphabet from './subcomponents/Alphabet'
import axios from 'axios'
export default {
  components: {
    CityHeader,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: []
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(res => {
          if (res.data.ret) {
            var data = res.data.data
            this.cities = data.cities
            this.hotCities = data.hotCities
          }
        })
    }
  },
  created () {
    this.getCityInfo()
  }
}
</script>
<style>
</style>
