<template>
  <div class="home container-fluid">
    <div class="row">
      <div class="col text-center">
        <h1>VUE-FLIX</h1>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <form @submit.prevent="search" class='form-group'>
          <input type="text" placeholder="Title...." v-model="query" required>
          <button type="submit" class="btn btn-info">Search</button>

        </form>
      </div>
    </div>
    <results>
    </results>

  </div>
</template>

<script>

  import Results from '@/components/Results.vue'
  export default {
    name: 'home',
    data() {
      return {
        query: ''
      }
    },
    computed: {


    },
    methods: {
      search() {
        this.$store.dispatch('searchApi', this.query)
      }
    },
    components: {
      Results

    }
  }
</script>

<style>
  .home {
    background-color: green;
  }
</style>