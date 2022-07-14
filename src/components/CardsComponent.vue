<template>
  <li class="card">
    <div class="poster">
      <img v-if="item.poster_path" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
      <img v-else src="../assets/img/placeholder_poster.png" alt="">
    </div>

    <ul>
      <!-- title -->
      <li>
        Title: {{item.title ? item.title : item.name}}
      </li>

      <!-- original title -->
      <li>
        Original Title: {{item.original_title ? item.original_title : item.original_name}}
      </li>

      <!-- language -->
      <!-- SE l'immagine della bandiera è presente allora la stampo,
      ---- ALTRIMENTI stampo il nome della lingua originale -->
      <li class="lang">
        Language: 
        <img v-if="flags.includes(item.original_language)" class="flag" :src="require(`../assets/img/${item.original_language}.png`)" :alt="item.original_language">
        <span v-else>{{item.original_language}}</span>
      </li>

      <!-- vote -->
      <li class="vote-average">
        Vote:
        <i v-for="n in stars(item.vote_average)" :key="n" class="fas fa-star"></i>
        <i v-for="n in 5 - stars(item.vote_average)" :key="n" class="far fa-star"></i>
      </li>
    </ul>
  </li>
</template>

<script>

export default {
  name: "CardsComponent",
  data() {
    return {
      flags: ['it', 'fr', 'en']
    }
  },
  props: {
    item: Object
  },
  methods: {
    stars(original_vote) {
      // divido il numero per due e lo arrotondo
      return Math.round(original_vote / 2);
    }
  }
}
</script>

<style lang="scss" scoped>
  .card {
    background-color: gray;
    width: calc((100% / 3) - 5px);
    padding: 5px;
    margin: 2.5px;

    .flag {
      width: 30px;
      vertical-align: middle;
      display: inline-block;
    }

    ul {

      li {
        padding-block: 0.15rem;
      }

      .vote-average {
        
        i {
          color: goldenrod;
        }
      }
    }

  }
</style>