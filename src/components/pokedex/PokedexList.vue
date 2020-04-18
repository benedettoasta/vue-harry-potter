<template>
  <div class="pokedex_list">
    <b-table sticky-header head-variant="light"
      :items="this.items.results"
      :fields="this.fields"
      @row-clicked="getItemSelected"
    >
 

    </b-table>
<!--
    <ul>
      <li v-for="(item, index) in this.items.results" :key="index">
        {{ item.name }}
        <span v-show="false">{{ item.url }}</span>
      </li>
    </ul>
-->
  </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'PokedexList',
    props: [
      "fields",
      "items",
    ],
    
    methods:{
      getItemSelected: function(event) {
        var itemSelected = {};
        axios.get(event.url)
        .then(response => {
          // JSON responses are automatically parsed.
          itemSelected = response.data;
          this.$emit("select-item",{ "itemSelected": itemSelected });
        })
        .catch(e => {
          this.errors.push(e)
        });
      }
    }
}
</script>

<style>

</style>