<template>
    <div class="alphabet">
      <ul>
        <li class="border-bottom" v-for="bet in list" :key="bet.index" :ref="bet.name" @click="change(bet)" @touchstart="handleTouchstart" @touchmove="handleTouchmove" @touchend="handleTouchend">{{bet.name}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'alphabetList',
  data () {
    return {
      touchstatus: false, // 触碰状态
      startY: 0, // 第一个字母距离顶部的距离
      timer: null
    }
  },
  props: [
    'list'
  ],
  updated () {
    // 计算第一个字母距离顶部的距离
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    change (bet) {
      this.$emit('letterChange', bet)
    },
    // 手指触碰
    handleTouchstart () {
      this.touchstatus = true
    },
    // 手指滑动
    handleTouchmove (e) {
      if (this.touchstatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          // 计算当前点击的字母距离顶部的距离
          const currentY = e.touches[0].clientY - 88
          // 计算当前点击的字母与第一个字母的间距差
          const index = Math.floor((currentY - this.startY) / 20)
          // 抛出当前滑动到的字母对象
          if (index >= 0 && index < this.list.length) {
            this.$emit('letterChange', this.list[index])
          }
        })
      }
    },
    // 手指滑动结束
    handleTouchend () {
      this.touchstatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .alphabet
    position: fixed
    display: flex
    flex-direction: column
    justify-content: center
    right: .1rem
    top: 1.78rem
    bottom: 0
    color: #999
    font-size: .3rem
    text-align: center
    li
      line-height: .4rem
      color: $bgColor

</style>
