<template>
    <div class="alphabet">
      <ul>
        <li v-for="bet in list" :key="bet.index">{{bet.name}}</li>
      </ul>
    </div>
</template>

<script>
export default {
  name: 'alphabetList',
  props: [
    'list'
  ]
}
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .alphabet
    position: fixed
    display: flex
    flex-direction: column
    justify-content: center
    right: .1rem
    top: 1.78rem
    bottom: 0
    color: #999
    font-size: .3rem
    text-align: center
    li
      padding: .04rem 0
      color: $bgColor

</style>
