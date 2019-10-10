<template>
  <div>
    <Logo />
    <section class="hero is-dark is-fullheight-with-navbar">
      <div class="hero-body">
        <div class="container has-text-centered">
          <Search v-on:search-result="setMovies" />
          <MovieCards :movies="movies" />
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Search from '~/components/Search.vue'
import MovieCards from '~/components/MovieCards.vue'

export default {
  components: {
    Logo,
    Search,
    MovieCards
  },

  data() {
    return {
      movies: []
    }
  },
  mounted() {},

  methods: {
    setMovies: function(movies) {
      console.log(movies)
      this.movies = []
      this.movies.push(...movies)
    }
  },

  watch: {},

  computed: {}
}
</script>

<style>
</style>
