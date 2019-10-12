<template>
  <div class="box">
    <div class="field has-addons has-addons-centered" @keyup.enter="search">
      <div class="control is-expanded">
        <input class="input" type="text" placeholder="Find a movie" v-model="searchValue" />
      </div>
      <div class="control">
        <a class="button" v-on:click="search">Search</a>
      </div>
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
        let url = this.searchOmdbUrl + this.searchValue
        const page1 = await this.$axios.$get(url)
        url = url + '&page=2'
        const page2 = await this.$axios.$get(url)
        const response = page1.Search.concat(page2.Search)

        this.$emit('search-result', response)
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