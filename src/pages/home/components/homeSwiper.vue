<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="swiper in swiperList" :key="swiper.id">
        <img class="swiper-img" :src="swiper.imageUrl"/>
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
      },
      swiperList: [
        { id: 0, imageUrl: 'http://img.ybl-group.com/ybl_1531735466013' },
        { id: 1, imageUrl: 'http://img.ybl-group.com/ybl_1532944137139' },
        { id: 2, imageUrl: 'http://img.ybl-group.com/ybl_1532686817592' }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color: white !important
  .wrapper
    overflow: hidden
    height: 0
    padding-bottom: 56%
    background-color: #eee
  .swiper-img
    width: 100%
</style>
