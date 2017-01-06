<template>

    <search-bar v-bind:type="type"> </search-bar>

</template>

<script>
  import search from '../components/search-bar.vue'
  export default {
    name: 'index',
    components: {
      'search-bar': search
    },
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        type: true
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

