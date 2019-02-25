<template>
  <div class="city">
    <city-header></city-header>
    <city-list
      :cities="cities"
      :hotCities="hotCities"
      :letter="letter"
    ></city-list>
    <city-alphabet
      :cities="cities"
      @Change="handleChange"
    ></city-alphabet>
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
      hotCities: [],
      letter: ''
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
    },
    handleChange (letter) {
      this.letter = letter
    }
  },
  created () {
    this.getCityInfo()
  }
}
</script>
<style>
</style>
