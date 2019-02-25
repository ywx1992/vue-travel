<template>
  <div class="city">
    <city-header></city-header>
    <city-list></city-list>
  </div>
</template>
<script>
import CityHeader from './subcomponents/Header'
import CityList from './subcomponents/List'
export default {
  components: {
    CityHeader,
    CityList
  }
}
</script>
<style>
</style>
