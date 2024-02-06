<script>
import AppItemsSection from './AppItemsSection.vue';
export default {
    // Logica Javascript
    name: 'AppMain',

    components: { AppItemsSection }
};
</script>
 
<template>
    <main>
        <div class="cards-box container">

            <AppItemsSection />

        </div>
    </main>
</template>
 
<style lang="scss" scoped>
/* Style */
.cards-box {
    background-color: whitesmoke;
    border-radius: 20px;
    padding: 20px;
}
</style>