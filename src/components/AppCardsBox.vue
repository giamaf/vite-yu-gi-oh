<script>
import AppItemsSection from './AppItemsSection.vue';
export default {
    // Logica Javascript
    name: 'AppCardsBox',

    components: {
        AppItemsSection
    }
};
</script>
 
<template>
    <!-- Template -->
    <main class="">
        <div class="cards-box container">

            <AppItemsSection />

        </div>
    </main>
</template>
 
<style lang="scss" scoped>
/* Style */

main {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: brown;
    height: 100vh;

    .cards-box {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: whitesmoke;
        width: 100%;
        height: 400px;
        border-radius: 20px;
        padding: 30px 20px;

    }
}
</style>