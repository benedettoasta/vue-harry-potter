<template>
  <header class="pokedex_header">
    <b-img v-bind="mainProps" src="@/assets/Pokédex_logo.png" center />
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