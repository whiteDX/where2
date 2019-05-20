<template>
  <div>
    <ul class="list">
        <li class="item"
            v-for="(item,key) of cities"
            :key="key"
            :ref="key"
            @click="handleLetterClick"
            @touchstart="handleTouchStart"
            @touchmove="handleTouchMove"
            @touchend="handleTouchEnd"
        >{{key}}</li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'CityAlphabet',
    props:{cities:Object},
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
    methods: {
      handleLetterClick (e) {
        this.$emit('change', e.target.innerText)
      },
      handleTouchStart () {
        this.touchStatus = true
      },
      handleTouchMove (e) {
          if(this.touchStatus) {
            const startY=this.$refs['A'][0].offsetTop
            const touchY = e.touches[0].clientY - 79
            const index = Math.floor(touchY - this.startY) / 20
            if (index >= 0 && index < this.letters.length) {
              this.$emit('change', this.letters[index])
            }
          }
      },
      handleTouchEnd () {
        this.touchStatus = false
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .list
    position absolute
    right 0
    top 1.58rem
    bottom 0
    display flex
    width .4rem
    flex-direction column
    justify-content center
    .item
      text-align center
      line-height .4rem
      color $bgColor
</style>
