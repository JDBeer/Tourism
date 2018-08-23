<template>
  <div>
   <city-head></city-head>
   <div class="wrapper" ref="wrapper">
     <div>
       <top-list :hotList="hotCityList" ></top-list>
       <city-list :alphabeList="alphabeList" :cityList="cityList" :selectedBet="selectedBet" @srcollElement="srcoll"></city-list>
     </div>
   </div>
   <alphabet-list :list="alphabeList" @letterChange="letterChange"></alphabet-list>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import cityHead from './components/cityHeader'
import topList from './components/topList'
import cityList from './components/cityList'
import alphabetList from './components/alphabetList'
import axios from 'axios'

export default {
  name: 'index',
  components: {
    cityList,
    cityHead,
    topList,
    alphabetList
  },
  data () {
    return {
      hotCityList: [], // 热门城市
      alphabeCityList: [], // 字母城市列表
      alphabeList: [], // 字母数组
      cityList: [], // 城市数组
      scroll: null, // 滑动列表
      selectedBet: null // 当前选择的字母
    }
  },
  methods: {
    getData () {
      axios.get('api/city.json').then(this.getCitySucc)
    },
    getCitySucc (res) {
      if (res.data.ret) {
        this.hotCityList = res.data.data.hotCities
        this.alphabeCityList = res.data.data.cities
        this.alphabeList = this.getAlphabeList(this.alphabeCityList)
        this.cityList = this.getCityList(this.alphabeCityList)
      }
    },
    // 字母数组
    getAlphabeList (map) {
      const keys = []
      let index = 0
      for (let obj in map) {
        let dic = {}
        dic.id = index
        dic.name = obj
        keys.push(dic)
        index++
      }
      return keys
    },
    // 城市数组
    getCityList (map) {
      const citys = []
      for (let obj in map) {
        citys.push(map[obj])
      }
      return citys
    },
    // 字母变化
    letterChange (bet) {
      this.selectedBet = bet.name
    },
    // 列表滑动
    srcoll (element) {
      this.scroll.scrollToElement(element)
    }
  },
  mounted () {
    this.getData()
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper
    position: absolute
    top: 1.78rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden

</style>
