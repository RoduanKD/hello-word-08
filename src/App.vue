<template>
  <div id="app">
    <hero-section />
    <posts-section />
  </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue'
import PostsSection from './components/PostsSection.vue'

export default {
  name: 'App',
  components: {
    HeroSection,
    PostsSection
  },

}
</script>

<style>
/* @import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"; */
@import '../node_modules/bulma/css/bulma.min.css';
</style>
