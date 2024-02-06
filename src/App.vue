<script>
import axios from 'axios';
import { store } from './assets/data/store.js';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
const secondEndopoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1';
import AppHeader from './AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  // Logica Javascript
  name: 'Pokévuex',

  data: () => ({
    store
  }),

  components: { AppHeader, AppMain },

  methods: {
    fetchPokemons(data) {
      axios.get(data).then(res => {
        //Inserisco la risposta dell'API nello STORE
        store.pokemons = res.data.docs;
      })
    },

    fetchTypes(data) {
      axios.get(data).then(res => {

        store.types = res.data;
      })
    },

    searchType(type) {
      let searchEndpoint = '';
      if (type && type !== 'All') {
        searchEndpoint = `https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=${type}&sort[number]=desc`;
      } else {
        searchEndpoint = endpoint
      }
      this.fetchPokemons(searchEndpoint)
    },
  },

  created() {
    this.fetchPokemons(endpoint);
    this.fetchTypes(secondEndopoint);
  },

};
</script>
 
<template>
  <div class="wrapper">
    <AppHeader @search-pokemon="searchType" @reset-data="searchType" />
    <AppMain />
  </div>
 </template>

<style lang="scss" scoped>
/* Style */
@use './assets/scss/style.scss';
</style>
