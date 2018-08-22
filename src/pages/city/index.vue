<template>
  <div>
   <city-head></city-head>
   <top-list :hotList="hotCityList"></top-list>
   <city-list :alphabeList="alphabeList" :cityList="cityList"></city-list>
   <alphabet-list :list="alphabeList"></alphabet-list>
  </div>
</template>

<script>
import cityHead from './components/cityHeader'
import topList from './components/topList'
import cityList from './components/cityList'
import alphabetList from './components/alphabetList'
import axios from 'axios'

export default {
  name: 'index',
  components: {
    cityHead,
    topList,
    cityList,
    alphabetList
  },
  data () {
    return {
      hotCityList: [], // 热门城市
      alphabeCityList: [], // 字母城市列表
      alphabeList: [], // 字母数组
      cityList: [] // 城市数组
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
    getCityList (map) {
      const citys = []
      for (let obj in map) {
        citys.push(map[obj])
      }
      return citys
    }

  },
  mounted () {
    this.getData()
  }
}
</script>

<style lang="stylus" scoped>

</style>
