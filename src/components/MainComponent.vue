<template>
    <section class="movies-container">
        <!-- cards container -->
        <ul class="movie-cards">
            <CardsComponent v-for="card in movieCards" :key="card.id" :item="card"/>
        </ul>
    </section>
</template>

<script>
import CardsComponent from './CardsComponent.vue';

export default {
    name: "MainComponent",
    components: {
        CardsComponent
    },
    props: {
        movieCards: Array,
        searching: Boolean
    }

}
</script>

<style lang="scss" scoped>
    .movies-container {
        width: 80%;
        margin: 0 auto;
        padding-top: 3rem;

        .movie-cards {
            display: flex;
            flex-wrap: wrap;
        }
    }
</style>