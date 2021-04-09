<template>
  <section class="beer-list" v-if="films.length">
    <film-list-item
    v-for="(film, index) in films"
    :film="film"
    :key="index"
    />

  </section>
</template>

<script>

import FilmListItem from './FilmListItem.vue'
export default {
    name: 'film-list',
    props: ["films"],
    components: {
      "film-list-item": FilmListItem
    }

}
</script>

<style scoped>

</style>