<template>
  <div class="columns is-multiline">
    <div class="column is-one-quarter" v-for="(movie, index) in movies" :key="index">
      <div class="card">
        <div class="card-image">
          <figure class="image is-9by16">
            <img :src="movie.Poster" alt="Poster" />
          </figure>
        </div>
        <div class="card-content">
          <div class="content">
            <p>{{ movie.Title }}</p>
            <p>{{ movie.Type }}</p>
            <br />
            <time datetime="2016-1-1">{{ movie.Year }}</time>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      default: []
    }
  }
}
</script>

<style>
</style>