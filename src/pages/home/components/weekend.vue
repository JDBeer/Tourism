<template>
  <div>
    <div class="weekend-title">周末去哪儿</div>
    <ul class="container">
      <li v-for="item in list" :key="item.id">
        <img :src="item.imgUrl"/>
        <p class="title">{{item.title}}</p>
        <p class="desprition">{{item.desc}}</p>
      </li>
    </ul>
  </div>

</template>

<script>
export default {
  name: 'weekend',
  props: [
    'list'
  ]
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
