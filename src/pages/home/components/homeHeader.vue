<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-xiangzuo"></span>
    </div>
    <div class="head-input">
      <span class="iconfont icon-sousuo search-icon"></span>
      <input class="input" type="text" placeholder="请输入城市、景点、游玩主题"/>
    </div>
    <div class="head-right" @click="pushToCity">{{city}}<span class="iconfont icon-jiantou arrow"></span></div>
  </div>
</template>

<script>
export default {
  name: 'homeHeader',
  props: [
    'city'
  ],
  methods: {
    pushToCity () {
      this.$router.push({path: './city'})
    }
  }
}
</script>

<style lang="stylus" scoped>
  /*可通过～@代替../../.. 找到src目录*/
  @import '~styles/varibles.styl'
  .header
    position: relative
    height: .86rem
    background-color: $bgColor
    display: flex
    .header-left
      display: inline-block
      width: .70rem
      height: .86rem
      line-height: .86rem
      color: white
      text-align: center
    .head-input
      position: relative
      display: inline-block
      flex: 1
      margin: .12rem 1.38rem .12rem .12rem
      padding-left: .6rem
      background-color: white
      .search-icon
        position: absolute
        left: .14rem
        top: .14rem
      .input
        width: 100%
        height: 100%
    .head-right
      position: absolute
      right: 0
      top: 0
      width: 1.26rem
      height: .86rem
      line-height: .86rem
      color: white
      text-align: center
      .arrow{
        position: relative;
        top: 0.02rem;
        margin-left: .1rem;
      }
</style>
