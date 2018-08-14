<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul class="container">
      <li v-for="item in weekendList" :key="item.id">
        <img :src="item.imageUrl"/>
        <p class="title">{{item.title}}</p>
        <p class="desprition">{{item.desprition}}</p>
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'weekend.vue',
  data () {
    return {
      weekendList: []
    }
  },
  methods: {
    getList () {
      let arr = []
      for (let i = 0; i < 3; i++) {
        var obj = { id: i, imageUrl: 'http://img.ybl-group.com/ybl_1531735466013', title: '大洋圣地海洋公园', desprition: '与动物嬉戏，共享和谐人生' }
        arr.push(obj)
      }
      this.weekendList = arr
    }
  },
  created () {
    this.getList()
  }
}
</script>

<style lang="stylus" scoped>
  .weekend-title
    padding: .3rem
    color: #333
    background-color: #eee
    margin-top: .1rem
  .container
    background-color: white
    img
      width: 100%
      height: auto
    .title
      margin-top: .2rem
      padding-left: .15rem
      font-size: .32rem
      color: #333
    .desprition
      padding-left: .15rem
      color: #999
      margin-top: .2rem
      margin-bottom: .2rem
</style>
