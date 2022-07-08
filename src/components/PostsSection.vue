<template>
  <section class="section">
    <div class="container">
      <div class="columns is-multiline">
        <div class="column is-4-desktop" v-for="(post, i) in displayedPosts" :key="i">
          <post-card v-bind:title="post.title" v-bind:body="post.body">
            <template #header>
              <h1 class="title is-1" style="color:red">{{ post.title }}</h1>
            </template>
            <div class="columns">
              <div class="column is-6"><img :src="post.image" alt=""></div>
              <div class="column is-6" v-text="post.body"></div>
            </div>
          </post-card>
        </div>
      </div>
      <button class="button is-primary" @click="prevPage" v-bind:disabled="from === 0">Previous</button>
      <button class="button is-primary" @click="nextPage" v-bind:disabled="to >= posts.length">Next</button>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
import PostCard from './PostCard.vue'

export default {
  components: { PostCard },
  data: () => ({
    posts: [
      {
        title: 'Testing',
        image: 'data:image/jpeg;base64,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',
        body: 'lorem'
      }
    ],
    from: 0,
    to: 15,
  }),

  async created() {
    const res = await axios.get('https://jsonplaceholder.typicode.com/posts')
    this.posts = res.data
  },

  computed: {
    displayedPosts() {
      return this.posts.slice(this.from, this.to)
    }
  },

  methods: {
    prevPage() {
      if (this.from !== 0) {
        this.from -= 15
        this.to -= 15
      }
    },

    nextPage() {
      if (this.to < this.posts.length) {
        this.from += 15
        this.to += 15
      }
    }
  }
}
</script>

<style>

</style>