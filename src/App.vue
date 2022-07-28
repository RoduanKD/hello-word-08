<template>
  <div id="app">
    <hero-section />
    <div class="container">
      <div class="field">
        <div class="control">
          <input class="input is-primary" type="text" v-model="name">
        </div>
      </div>    <!-- name -->
      <div class="field">
        <div class="control"><textarea class="textarea" v-model="description"></textarea></div>
      </div>  <!-- descrtion -->
    </div>
    <about-section v-bind:name="name" :description="description" />
    <posts-section />
  </div>
</template>

<script>
import HeroSection from './components/HeroSection.vue'
import PostsSection from './components/PostsSection.vue'
import AboutSection from './components/AboutSection.vue'

export default {
  name: 'App',
  components: {
    HeroSection,
    PostsSection,
    AboutSection
  },

  data: () => ({
    name: '',
    description: '',
  })
}
</script>

<style>
/* @import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"; */
@import '../node_modules/bulma/css/bulma.min.css';
</style>
