<template>
<!--
  <div class="pokedex_detail">
    <b-card
      :title="item.name"
      :img-src="item.sprites.front_default"
      img-alt="Image"
      img-top
      tag="article"
      style="max-width: 20rem;"
      class="mb-2"
    >
    </b-card>
  </div>
-->
  <b-container fluid class="pokedex_detail p-0">
    <b-row class="no-gutters" align-v="start">
      <b-col>
        <b-img v-bind="mainProps" :src="item.sprites.front_default" center />
        <h2>{{item.name | capitalize}}</h2>
      </b-col>
    </b-row>
  </b-container>
  
</template>

<script>
export default {
    name: 'PokedexDetail',
    data(){
      return {
        mainProps: {
          center: true,
          height: 200,
          class: 'pokedex__logo'
        }
      }
    },
    props: [
      "item",
    ],
}
</script>

<style>

</style>