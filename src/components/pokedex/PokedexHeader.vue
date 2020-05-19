<template>
  <header class="pokedex_header">
    <b-img v-bind="mainProps" :src="require('../../assets/Pokedex_logo.png')" />
  </header>
</template>

<script>
export default {
    name: 'PokedexHeader',
    
    data() {
      return {
        mainProps: {
          center: true,
          height: 50,
          class: 'pokedex__logo'
        }
      }
    }
    
}
</script>

<style lang="scss">

</style>