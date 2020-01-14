<template>
  <div class="flip" :class="{'running': isFlipping}" ref="flip">
    <div class="digital front" :data-number="frontNumber" ref="frontNode"></div>
    <div class="digital back" :data-number="backNumber" ref="backNode"></div>
  </div>
</template>

<script>
export default {
  name: '',
  props: {
    timeString: {
      type: String,
      default: '0'
    }
  },
  data() {
    return {
      isFlipping: false,
      frontNumber: 0,
      backNumber: 1,
      duration: 600,
    }
  },
  watch: {
    timeString: {
      immediate: true,
      handler(val, oldVal) {
        if (this.oldVal !== val) {
          this.flipDown(oldVal, val)
        }
      }
    }
  },
  mounted() {
    this.flipNode = this.$refs.flip
  },
  methods: {
    flipDown(currentTime, nextTime) {
      if (this.isFlipping) {
        return false
      }
      this.isFlipping = true
      this.frontNumber = currentTime
      this.backNumber = nextTime
      setTimeout(() => {
        this.isFlipping = false
        this.frontNumber = nextTime
      }, this.duration)
    }
  }
}
</script>