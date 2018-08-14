<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="swiper in list" :key="swiper.id">
        <img class="swiper-img" :src="swiper.imgUrl"/>
        </swiper-slide>
        <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default{
  name: 'homeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: { el: '.swiper-pagination' },
        loop: true
      }
    }
  },
  props: [
    'list'
  ]
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color: white !important
  .wrapper
    background-color: #eee
  .swiper-img
    width: 100%
</style>
