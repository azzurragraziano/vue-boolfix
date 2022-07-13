<template>
  <div id="app">
    
    <!-- header -->
    <header>
      <HeaderComponent @userInput="searchElement"/>
    </header>

    <!-- main -->
    <main>
      <MainComponent :movieCards="movies" :searching="searchStarted"/>
    </main>

  </div>
</template>

<script>
import axios from "axios";
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';


export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent
  },
  data() {
    return {
      apiUrl: 'https://api.themoviedb.org/3/search/',
      apiKey: '24d94b49d4155e1ec947ec02316b0346',
      movies: [],
      series: [],
      allResults: [],
      searchStarted: false,
    }
  },
  computed: {
    computedResults() {
      return this.movies;
    }
  },
  methods: {

    // getMovies riceve in input i parametri ed effettua la chiamata axios
    getMovies(apiParams) {
      axios.get(this.apiUrl + 'movie', apiParams).then((response) => {
        this.movies = response.data.results;
        this.allResults = [...this.movies];
        this.searchStarted = true;
      })
    },
    searchElement(searchText) {

      //oggetto di parametri: apiKey, parola digitata dall'utente e lingua
      const paramsObj = {
        params: {
          api_key: this.apiKey,
          query: searchText,
          language: 'it-IT'
        }
      };

      // passiamo il parametro a getMovies
      this.getMovies(paramsObj);
    }
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  main {
    background-color: #292828;
    height: calc(100vh - 4rem);
  }

  li {
    list-style-type: none;
  }
</style>
