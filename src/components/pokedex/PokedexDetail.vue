<template>
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
</template>

<script>
export default {
    name: 'PokedexDetail',
    props: [
      "item",
    ],
}
</script>

<style>

</style>