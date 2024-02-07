<script>
export default {
    // Javascript Logic
    name: 'AppSearch',

    data: () => ({
        typeSearched: '',
    }),

    emits: ['search-pokemon', 'reset-pokemons'],

    props: {
        options: Array,
        defaultLabel: String
    },

    methods: {
        submitForm() {
            this.$emit('search-pokemon', this.typeSearched)
        },

        resetForm() {
            this.typeSearched = '';
            this.$emit('reset-pokemons', this.typeSearched);
        },
    }
};
</script>
 
<template>
    <form @submit.prevent="submitForm" name="form">
        <select class="form-select" v-model="typeSearched">
            <option :value="defaultLabel">{{ defaultLabel }}</option>
            <option v-for="( option, i ) in  options " :key="i">{{ option }}
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
