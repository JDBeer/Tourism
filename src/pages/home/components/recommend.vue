<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul class="container">
      <li v-for="item in list" :key="item.id">
        <img :src="item.imgUrl"/>
        <div class="right-wrap">
          <p class="title">{{item.title}}</p>
          <p class="desprition">{{item.desc}}</p>
          <p class="price">{{item.pirce||'97'}}<span class="price-inset">起</span></p>
        </div>
      </li>
    </ul>
    <p v-if="checkBoxShow" class="check-all" @click="checkTap()">查看所有商品</p>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  data () {
    return {
      checkBoxShow: true
    }
  },
  methods: {
    checkTap: function () {
      // let plusArr = [];
      // for (let i = this.list.length; i < (this.list.length + 3); i++) {
      //   var obj = {
      //     id: i,
      //     imgUrl: 'https://img.ybl-group.com/ybl_1524491013746',
      //     title: '大洋圣地海洋公园',
      //     desc: '与动物嬉戏，共享和谐人生',
      //     pirce: '57'
      //   }
      //   plusArr.push(obj)
      // }
      // this.list.push(plusArr)
      this.checkBoxShow = false
    }
  },
  props: [
    'list'
  ]
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .recommend-title
    padding: .3rem
    color: #333
    background-color: #eee
    margin-top: .1rem
  .container
    background-color: white
    li
      position: relative
      padding: .2rem
      border-bottom: .01rem solid #D8D8D8
      img
        width: 1.7rem
        height: 1.7rem
  .right-wrap
    position: absolute
    left: 2.2rem
    top: .3rem
    right: .2rem
    .title
      font-size: .32rem
    .desprition
      color: #999
      margin-top: .2rem
    .price
      margin-top: .2rem
      color: orange
      font-size: .4rem
      .price-inset
        color: #999
        font-size: .25rem
        margin-left: .06rem
    .price:before
      content: '¥'
      font-size: .3rem
      margin-right: .06rem
  .check-all
    position: relative
    top: .06rem
    height: 1rem
    line-height 1rem
    vertical-align: middle
    text-align: center
    color: $bgColor
    font-size: .32rem

</style>
