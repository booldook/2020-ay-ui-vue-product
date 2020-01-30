<template>
  <div id="app">
    <nav-bar />
    <div class="container">
      <search-bar />
      <product />
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import NavBar from './components/NavBar.vue';
import Product from './components/Product.vue';

export default {
  name: 'app',
  components: {
    'search-bar': SearchBar,
    'nav-bar': NavBar,
    'product': Product,
  }
}
</script>

<style lang="less">

</style>
