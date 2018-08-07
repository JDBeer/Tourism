<template>
  <div class="wrap">
    <swiper>
      <!-- slides -->
      <swiper-slide>
        <ul>
          <li v-for="(icon,tag) in iconList" v-if="tag<=7" class="wrap-li" :key="icon.id">
            <img :src="icon.imageUrl"/>
            <p>{{icon.text}}</p>
          </li>
        </ul>
      </swiper-slide>
      <swiper-slide>
        <ul>
          <li v-for="(icon,tag) in iconList" v-if="tag>7" class="wrap-li" :key="icon.id">
            <img :src="icon.imageUrl"/>
            <p>{{icon.text}}</p>
          </li>
        </ul>
      </swiper-slide>
    </swiper>
  </div>

</template>

<script>
export default {
  name: 'homeIcons',
  data () {
    return {
      iconList: [
        { id: 0, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-1.png', text: '景点门票' },
        { id: 1, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-2.png', text: '滑雪季' },
        { id: 2, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-3.png', text: '泡温泉' },
        { id: 3, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-4.png', text: '动植物园' },
        { id: 4, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-5.png', text: '一日游' },
        { id: 5, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-6.png', text: '必游榜单' },
        { id: 6, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-7.png', text: '自然风光' },
        { id: 7, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-8.png', text: '全部' },
        { id: 8, imageUrl: 'https://img.ybl-group.com/appres/main-iconbox-9.png', text: '美食季' }
      ]
    }
  }
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
