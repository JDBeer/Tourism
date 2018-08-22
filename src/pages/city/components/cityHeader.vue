<template>
  <div>
    <div class="city-head">
      <router-link to="/">
        <div class="header-left">
          <span class="iconfont icon-xiangzuo"></span>
        </div>
      </router-link>
      <span>城市列表</span>
    </div>
    <div class="city-input">
      <input type="text" v-model="searchText" placeholder="输入城市名或拼音">
    </div>
  </div>
</template>

<script>
export default {
  name: 'cityHeader',
  data () {
    return {
      searchText: ''
    }
  }
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
  .city-input
    height: .8rem
    line-height: .8rem
    background: $bgColor
    text-align: center
    padding:0 .4rem .08rem .2rem
    input
      display: inline-block
      padding-left: .2rem
      color: #333
      width: 100%
      height: 80%
      font-size: .28rem

</style>
