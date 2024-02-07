<script>
import { store } from './assets/data/store.js'
import AppSearch from './components/AppSearch.vue';
export default {

    data: () => ({
        store
    }),

    components: { AppSearch },

    emits: ['types', 'search-pokemon', 'reset-data'],

};
</script>
 
<template>
    <header>
        <div class="container d-flex justify-content-end">
            <AppSearch @search-pokemon="$emit('search-pokemon', $event)" @reset-pokemons="$emit('reset-data', $event)"
                :default-label="'All'" :options="store.types" />
        </div>
    </header>
</template>
     
<style lang="scss" scoped>
/* Style */
header {
    padding: 20px 0;
}
</style>
