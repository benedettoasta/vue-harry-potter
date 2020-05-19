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
        <b-img v-bind="mainProps" :src="this.item.sprites.front_default" center />
        <h2>{{item.name | capitalize}}</h2>
        <b-badge class="m-1" v-for="(item, name, index) in this.item.types" :key="index" pill variant="dark"> {{ item.type.name | capitalize }} </b-badge>

        <b-container fluid class="pokedex_detail_stats p-0">
          <b-row class="no-gutters" align-v="start">
            <b-col cols="6">
              <b-card-group deck class="m-2">
                <b-card border-variant="dark" header="" align="center">
                  <b-card-text 
                    v-for="(value, name, index) in  ['id','name','height','weight','base_experience','is_default']" 
                    :key="index"
                    class="p-0 m-0"
                  >
                    <strong>{{ value | snakeToSpace | capitalize }}</strong>: {{ item[value] }}
                  </b-card-text>
                </b-card>
              </b-card-group>
            </b-col>
            <b-col cols="6">
              <b-card-group deck class="m-2">
                <b-card border-variant="dark" header="" align="center">
                  <b-card-text 
                    v-for="(item, name, index) in this.item.stats" 
                    :key="index"
                    class="p-0 m-0"
                  >
                    <strong>{{ item.stat.name | capitalize }}</strong>: {{ item.base_stat }}
                  </b-card-text>
                </b-card>
              </b-card-group>
            </b-col>
          </b-row>
        </b-container>
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
          height: 150,
          class: 'pokedex__logo'
        }
      }
    },
    props: [
      "item",
    ],
}
</script>

<style scoped>
.pokedex_detail div{
    
    height: auto;

}
</style>