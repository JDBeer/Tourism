<template>
  <div class="wrap">
    <swiper>
      <!-- slides -->
      <swiper-slide>
        <ul>
          <li v-for="(icon,tag) in list" v-if="tag<=7" class="wrap-li" :key="icon.id">
            <img :src="icon.imgUrl"/>
            <p>{{icon.desc}}</p>
          </li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <ul>
          <li v-for="(icon,tag) in list" v-if="tag>7" class="wrap-li" :key="icon.id">
            <img :src="icon.imgUrl"/>
            <p>{{icon.desc}}</p>
          </li>
        </ul>
      </swiper-slide>
    </swiper>
  </div>

</template>

<script>
export default {
  name: 'homeIcons',
  props: [
    'list'
  ]
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixmin.styl'
  .wrap
    padding-bottom: .3rem
    background-color: white
    min-height: 2rem
    .wrap-li
      display: inline-block
      width: 25%
      margin-top: .3rem
      text-align: center
      img
        width: .86rem
      p
        margin-top .2rem
        color: #333
        ellipsis()
</style>
