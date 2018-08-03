<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
  </div>
</template>

<script>
import homeHeader from './components/homeHeader'
import homeSwiper from './components/homeSwiper'
import homeIcons from './components/homeIcons'
export default {
  name: 'home',
  components: {
    homeHeader,
    homeSwiper,
    homeIcons
  }
}
</script>

<style>
</style>
