<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import homeHeader from './components/homeHeader'
import homeSwiper from './components/homeSwiper'
import homeIcons from './components/homeIcons'
import homeRecommend from './components/recommend'
import homeWeekend from './components/weekend'
export default {
  name: 'home',
  components: {
    homeHeader,
    homeSwiper,
    homeIcons,
    homeRecommend,
    homeWeekend
  }
}
</script>

<style>
</style>
