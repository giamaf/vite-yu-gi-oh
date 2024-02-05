<script>
import AppCard from './AppCard.vue';
export default {
    // Logica Javascript
    name: 'AppItemsSection',

    components: {
        AppCard
    }
};
</script>
 
<template>
    <!-- Template -->
    <section class="items-box">
        <div class="row row-cols-5">
            <div class="col">
                <AppCard />
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
}
</style>