<template>
  <div class="city-head">
    <router-link to="/">
      <div class="header-left">
        <span class="iconfont icon-xiangzuo"></span>
      </div>
    </router-link>
    <span>城市列表</span>
  </div>
</template>

<script>
export default {
  name: 'cityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .city-head
    position: relative
    height: $headHeight
    line-height: $headHeight
    background: $bgColor
    color: #fff
    font-size: .30rem
    text-align: center
    .header-left
      position: absolute
      display: inline-block
      left: 0
      top: 0
      width: .70rem
      height: .86rem
      line-height: .86rem
      color: white

</style>
