<script>
import { store } from '../assets/data/store';
import AppCard from './AppCard.vue';
export default {
    // Logica Javascript
    name: 'AppItemsSection',

    data: () => ({
        store
    }),

    components: {
        AppCard
    }
};
</script>
 
<template>
    <section class="items-box">
        <div class="row row-cols-5 gy-3">
            <div class="col" v-for="pokemon in store.pokemons" :key="pokemon._id">
                <AppCard :id="pokemon._id" :image="pokemon.imageUrl" :number="pokemon.number" :name="pokemon.name"
                    :type="pokemon.type1" :color="pokemon.color" />
            </div>
        </div>
    </section>
</template>
 
<style lang="scss" scoped>
/* Style */
.items-box {
    background-color: grey;
    border-radius: 20px;
    width: 100%;
    height: 100%;
    padding: 20px;
}
</style>