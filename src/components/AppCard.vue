<script>
export default {
    // Logica Javascript
    name: 'AppCard',
    props: {
        id: String,
        image: String,
        number: Number,
        name: String,
        type: String,
        color: String
    }
};
</script>
 
<template>
    <div class="card py-3 bg-all" :class="{
        'bg-green': type === 'Grass',
        'bg-blue': type === 'Water',
        'bg-red': type === 'Fire',
    }">
        <img :src="image" :alt="name" class="card-img-top rounded-circle mb-2">
        <div class="card-body text-center">
            <p>{{ number }}</p>
            <p class="pokemon-name">{{ name }}</p>
            <p class="type text-body-secondary">{{ type }}</p>
        </div>
    </div>
</template>
 
<style lang="scss" scoped>
/* Style */
.card {
    display: flex;
    justify-content: center;
    align-items: center;

    img {
        width: 100px;
        height: 100px;
        border: 1px solid lightgray;
    }
}

.card-body {
    padding: 0;

    * {
        margin: 0;
        font-size: 0.8rem;
    }

    .pokemon-name {
        font-weight: 600;
    }

    .type {
        font-weight: lighter;
        font-style: italic;
    }
}

.bg-all {
    background-color: blanchedalmond
}

.bg-green {
    background-color: rgb(193, 252, 232)
}

.bg-red {
    background-color: rgb(255, 206, 206);
}

.bg-blue {
    background-color: lightblue;
}
</style>