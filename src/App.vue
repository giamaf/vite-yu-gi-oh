<script>
import axios from 'axios';
import { store } from './assets/data/store.js';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import AppHeader from './AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  // Logica Javascript
  name: 'Pokévuex',

  components: { AppHeader, AppMain },

  created() {
    axios.get(endpoint).then(res => {
      //Inserisco la risposta dell'API nello STORE 
      store.pokemons = res.data.docs;
    })
  },
};
</script>
 
<template>
  <div class="wrapper">
    <AppHeader />
    <AppMain />
  </div>
 </template>

<style lang="scss" scoped>
/* Style */
@use './assets/scss/style.scss';
</style>
