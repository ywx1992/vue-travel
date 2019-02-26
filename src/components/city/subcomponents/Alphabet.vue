<template>
  <div class="alpha">
    <ul>
      <li v-for="item in letters"
          :key="item"
          :ref="item"
          @click="letterChange(item)"
          @touchstart.prevent="handleTouchstart"
          @touchmove="handleTouchmove"
          @touchend="handleTouchend"
      >{{item}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    letterChange (letter) {
      this.$emit('Change', letter)
    },
    handleTouchstart () {
      this.touchStatus = true
    },
    handleTouchmove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 83
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index <= this.letters.length) {
            this.$emit('Change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchend () {
      this.touchStatus = false
    }
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
