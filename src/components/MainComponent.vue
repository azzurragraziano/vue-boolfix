<template>
  <section>
    <h2>Film</h2>
    <div class="cards-container">
        <ul class="movie-card">
            <CardsComponent v-for="card in movieCards" :key="card.id" :item="card"/>
        </ul>
    </div>
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

<style>

</style>