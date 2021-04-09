<template>
  <div id="app">
    <p>Homepage!</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data() {
  return {
    movies: [],
    selectedMovie: null
    };
  },
  async mounted() {
    const res = await fetch('https://ghibliapi.herokuapp.com/films')
    const data = await res.json()
    this.movies = data
    console.log(this.movies)

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
