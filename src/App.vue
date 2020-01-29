<template>
  <div id="app">
    <nav-bar />
    <div class="container">
      <search-bar />
    </div>
  </div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import NavBar from './components/NavBar.vue';

export default {
  name: 'app',
  components: {
    'search-bar': SearchBar,
    'nav-bar': NavBar
  }
}
</script>

<style lang="less">

</style>
