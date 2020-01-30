<template>
  <div id="app">
    <nav-bar />
    <div class="container">
      <search-bar v-bind:query="query" v-on:@submit="onSubmit" />
      <product v-bind:query="query" />
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import NavBar from './components/NavBar.vue';
import Product from './components/Product.vue';

export default {
  name: 'app',
  data() {
    return {
      query: ''
    }
  },
  components: {
    'search-bar': SearchBar,
    'nav-bar': NavBar,
    'product': Product,
  },
  methods: {
    onSubmit(value) {
      this.query = value;
    }
  }
}
</script>

<style lang="less">

</style>
