<script>
import AppSearch from './components/AppSearch.vue';
export default {
    components: { AppSearch }
};
</script>
 
<template>
    <header>
        <div class="container d-flex justify-content-end">
            <AppSearch />
        </div>
    </header>
</template>
     
<style lang="scss" scoped>
/* Style */
header {
    padding: 20px 0;
}
</style>
