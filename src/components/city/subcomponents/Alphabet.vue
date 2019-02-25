<template>
  <div class="alpha">
    <ul>
      <li v-for="(value, key) in cities" :key="key">{{key}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    cities: Object
  }
}
</script>
<style lang="less" scoped>
  @import "~@/assets/styles/variables.less";
  .alpha{
    position: absolute;
    top: 1.66rem;
    right: 0;
    bottom: 0;
    width: 0.4rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    line-height: 0.4rem;
    color: @bgColor;

  }
</style>
