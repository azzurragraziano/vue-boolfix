<template>
    <main>
        <section class="container">
            <!-- section title -->
            <h2>Film</h2>

            <!-- cards container -->
            <ul class="movie-cards">
                <CardsComponent v-for="card in movieCards" :key="card.id" :item="card"/>
            </ul>
        </section>

        <section class="container">
            <!-- section title -->
            <h2>Series</h2>

            <!-- cards container -->
            <ul class="series-cards">
                <CardsComponent v-for="card in seriesCards" :key="card.id" :item="card"/>
            </ul>
        </section>
    </main>
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
        seriesCards: Array,
        searching: Boolean
    }

}
</script>

<style lang="scss" scoped>

main {
    background-color: #292828;
    min-height: calc(100vh - 100px);
  }
    .container {
        width: 80%;
        margin: 0 auto;
        padding-top: 3rem;

        .movie-cards, .series-cards {
            display: flex;
            flex-wrap: wrap;
        }
    }
</style>