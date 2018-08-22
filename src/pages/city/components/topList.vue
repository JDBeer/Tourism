<template>
  <div class="container">
    <div class="top-wrap">
      <p>您的位置</p>
      <div class="location-wrap"><span>杭州</span></div>
    </div>
    <div class="content-wrap">
      <p>热门城市</p>
      <ul>
        <li v-for="city in hotList" :key="city.id">{{city.name}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'topList',
  props: [
    'hotList'
  ]
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .container
    background-color: #f6f6f6
    .top-wrap
      p
        padding: .3rem
      .location-wrap
        background-color: white
        padding: .4rem .3rem
        span
          padding: .1rem .5rem
          border: .02rem solid $bgColor
          color: $bgColor
          font-size: .3rem
          border-radius: 4px
    .content-wrap
      background-color: white
      padding-bottom: .25rem
      p
        padding: .3rem
        background-color: #f6f6f6
      ul
        padding-right: .5rem
        background-color: white
      li
        display: inline-block
        margin-top: .25rem
        margin-left: 2.5%
        width: 30%
        padding: .1rem 0
        border-radius: 4px
        border: .02rem solid #eee
        color: #333
        font-size: .3rem
        text-align: center
</style>
