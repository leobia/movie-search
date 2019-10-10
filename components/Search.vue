<template>
  <div class="field has-addons has-addons-centered">
    <div class="control">
      <input class="input" type="text" placeholder="Find a movie" v-model="searchValue" />
    </div>
    <div class="control">
      <a class="button" v-on:click="search">Search</a>
    </div>
  </div>
</template>

<script>
import * as bulmaToast from 'bulma-toast'

export default {
  data() {
    return {
      searchValue: null,
      searchOmdbUrl: 'http://www.omdbapi.com/?apikey=ca5e425d&s='
    }
  },

  mounted() {},
  methods: {
    async search() {
      if (this.searchValue) {
        const url = this.searchOmdbUrl + this.searchValue
        const response = await this.$axios.$get(url)
        this.$emit('search-result', response.Search)
      } else {
        bulmaToast.toast({
          message: 'Type a valid keyword!',
          type: 'is-danger',
          position: 'bottom-center',
          animate: { in: 'fadeIn', out: 'fadeOut' }
        })
      }
    }
  }
}
</script>

<style>
</style>