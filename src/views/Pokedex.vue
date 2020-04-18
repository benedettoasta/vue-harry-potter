<template>
  <b-container fluid class="pokedex_container">
  <!-- Content here -->
    <b-row>
      <b-col>
        <pokedex-header />
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <pokedex-navbar />
      </b-col>
    </b-row>
    
    <b-row>
      <b-col cols="4">
        <pokedex-list />
      </b-col>
      <b-col cols="8">
        <pokedex-detail />
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <pokedex-footer />
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
// @ is an alias to /src
import PokedexHeader from '@/components/pokedex/PokedexHeader.vue'
import PokedexNavbar from '@/components/pokedex/PokedexNavbar.vue'
import PokedexList from '@/components/pokedex/PokedexList.vue'
import PokedexDetail from '@/components/pokedex/PokedexDetail.vue'
import PokedexFooter from '@/components/pokedex/PokedexFooter.vue'

export default {
  name: 'Pokedex',
  components: {
    PokedexHeader,
    PokedexNavbar,
    PokedexList,
    PokedexDetail,
    PokedexFooter
  }
}
</script>