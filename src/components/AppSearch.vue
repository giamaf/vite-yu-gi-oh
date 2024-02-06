<script>
import { store } from '../assets/data/store';
export default {
    // Javascript Logic
    name: 'AppSearch',

    data: () => ({
        store,
        typeSearched: '',
    }),

    emits: ['search-pokemon', 'reset-pokemons'],

    methods: {
        submitForm() {
            this.$emit('search-pokemon', this.typeSearched)
        },

        resetForm() {
            // this.typeSearched = '';
            this.$emit('reset-pokemons');
        },
    }
};
</script>
 
<template>
    <form @submit.prevent="submitForm" name="form">
        <select class="form-select" v-model="typeSearched">
            <option v-for="( type, i ) in  store.types " :key="i">{{ type }}
            </option>
        </select>
        <button class="btn btn-secondary" role="button">Cerca</button>
        <button class="btn btn-warning" role="button" @click="resetForm">Reset</button>
    </form>
</template>
 
<style lang="scss" scoped>
/* Style */
form {
    width: 25%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 5px;
}
</style>
