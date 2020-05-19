<template>
<!--
  <b-container fluid class="pokedex_container p-0 fill">
    <b-row class="no-gutters" align-v="start">
      <b-col>
        <pokedex-header />
      </b-col>
    </b-row>

    <b-row class="no-gutters h-100" align-v="center">
      <b-col cols="4">
        <pokedex-list 
          :items="pokemonList" 
          :fields="pokemonListFields"
          @select-item="setPokemonSelected">
        </pokedex-list>
      </b-col>
      <b-col cols="8">
        <pokedex-detail 
          :item="pokemonSelected"
          v-if="pokemonSelected !== false"
        >
        </pokedex-detail>
      </b-col>
    </b-row>

    <b-row class="no-gutters" align-v="end">
      <b-col>
        <pokedex-footer />
      </b-col>
    </b-row>
  </b-container>
  -->
  <div class="page">
   <pokedex-header />
   <b-container fluid class="pokedex_container p-0 fill">
      <b-row class="no-gutters h-100" align-v="start">
        <b-col cols="4">
          <pokedex-list 
            :items="pokemonList" 
            :fields="pokemonListFields"
            @select-item="setPokemonSelected">
          </pokedex-list>
        </b-col>
        <b-col cols="8">
          <pokedex-detail 
            :item="pokemonSelected"
            v-if="pokemonSelected !== false"
          >
          </pokedex-detail>
        </b-col>
      </b-row>
   </b-container>
   <pokedex-footer />
  </div>
</template>

<script>
// @ is an alias to /src
import PokedexHeader from '@/components/pokedex/PokedexHeader.vue'
//import PokedexNavbar from '@/components/pokedex/PokedexNavbar.vue'
import PokedexList from '@/components/pokedex/PokedexList.vue'
import PokedexDetail from '@/components/pokedex/PokedexDetail.vue'
import PokedexFooter from '@/components/pokedex/PokedexFooter.vue'

import axios from 'axios';

export default {
  data() {
    return {
      pokemonListFields: [
          '#',
          { 
            key: 'name', 
            label: 'Pokemon Name' 
          },
      ],
      pokemonList: {},
      pokemonSelected: false,
    }
  },

  name: 'Pokedex',
  components: {
    PokedexHeader,
    //PokedexNavbar,
    PokedexList,
    PokedexDetail,
    PokedexFooter
  },

  methods:{
    setPokemonSelected({itemSelected}){
      this.pokemonSelected = itemSelected;
    }
  },

  created() {
    axios.get(`https://pokeapi.co/api/v2/pokemon/?limit=151`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.pokemonList = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })
  },
}
</script>


<style lang="scss">


.pokedex{
  &_header, &_footer{
    background-color: red;
    height: 50;
  }
  &_container{
      height: calc(100% - 75px);

      div{
        height: 100%;
      }

  }
  &_detail{
      height: 100%;
  }
}

.page{
  height: 100%;
}

</style>
