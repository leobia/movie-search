<template>
  <div>
    <Logo />
    <section class="hero background is-fullheight-with-navbar">
      <div id="flow">
        <span class="flow-1"></span>
        <span class="flow-2"></span>
        <span class="flow-3"></span>
      </div>
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
body {
  background: #041221;
}

.background {
  background: #041221;
}

.box {
  background-color:rgba(255, 255, 255, 0.3);
}

#flow span {
  display: block;
  width: 200vw;
  height: 185vw;
  position: absolute;
  top: -180vw;
  left: -50vw;
  border-radius: 90vw;
  opacity: 0.6;
}
.flow-1 {
  background: #3281ff;
  -webkit-animation: rotating 20s linear infinite;
  -moz-animation: rotating 20s linear infinite;
  -ms-animation: rotating 20s linear infinite;
  -o-animation: rotating 20s linear infinite;
  animation: rotating 20s linear infinite;
}
.flow-2 {
  background: #f442ee;
  position: absolute;
  -webkit-animation: rotating 15s linear infinite;
  -moz-animation: rotating 15s linear infinite;
  -ms-animation: rotating 15s linear infinite;
  -o-animation: rotating 15s linear infinite;
  animation: rotating 15s linear infinite;
}
.flow-3 {
  background: #42eef4;
  position: absolute;
  -webkit-animation: rotating 7s linear infinite;
  -moz-animation: rotating 7s linear infinite;
  -ms-animation: rotating 7s linear infinite;
  -o-animation: rotating 7s linear infinite;
  animation: rotating 7s linear infinite;
}

@-webkit-keyframes rotating {
  from {
    -ms-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  to {
    -ms-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
@keyframes rotating {
  from {
    -ms-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    -webkit-transform: rotate(0deg);
    -o-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  to {
    -ms-transform: rotate(360deg);
    -moz-transform: rotate(360deg);
    -webkit-transform: rotate(360deg);
    -o-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
.rotating {
  -webkit-animation: rotating 2s linear infinite;
  -moz-animation: rotating 2s linear infinite;
  -ms-animation: rotating 2s linear infinite;
  -o-animation: rotating 2s linear infinite;
  animation: rotating 2s linear infinite;
}
</style>
