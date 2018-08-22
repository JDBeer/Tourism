<template>
    <div>
      <div v-for="(alphabet,index) in alphabeList" :key="alphabet.index">
        <p class="alphabet">{{alphabet.name}}</p>
        <ul style="padding-right: .5rem">
          <li class="city-li" v-for="city in cityList[index]" :key="city.id">{{city.name}}</li>
        </ul>
      </div>
    </div>
</template>

<script>
export default {
  name: 'cityList',
  props: [
    'alphabeList',
    'cityList'
  ]
}
</script>

<style lang="stylus" scoped>
  .alphabet
    background-color: #f6f6f6
    padding: .3rem
  .city-li
    padding: .3rem 0 .3rem .3rem
    background-color: white
    border-bottom: .5px solid #D8D8D8

</style>
