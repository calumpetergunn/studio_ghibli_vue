<template>
  <div id="app">
    <p>Homepage!</p>
    <film-list :films="films"/>
  </div>
</template>

<script>

import FilmList from './components/FilmList.vue'
import FilmListItem from './components/FilmListItem.vue'

export default {
  name: 'App',
  components: {
    "film-list": FilmList,
    "film-list-item": FilmListItem
  },
  data() {
  return {
    films: [],
    selectedMovie: null
    };
  },

  async mounted() {
    const res = await fetch('https://ghibliapi.herokuapp.com/films')
    const data = await res.json()
    this.films = data
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
