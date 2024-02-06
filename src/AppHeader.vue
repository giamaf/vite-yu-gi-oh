<script>
import AppSearch from './components/AppSearch.vue';
export default {
    components: { AppSearch },

    emits: ['search-pokemon', 'reset-data'],

};
</script>
 
<template>
    <header>
        <div class="container d-flex justify-content-end">
            <AppSearch @search-pokemon="$emit('search-pokemon', $event)" @reset-pokemons="$emit('reset-data', $event)" />
        </div>
    </header>
</template>
     
<style lang="scss" scoped>
/* Style */
header {
    padding: 20px 0;
}
</style>
