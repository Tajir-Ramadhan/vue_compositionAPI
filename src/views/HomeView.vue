<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <posts :posts="posts"/>
    </div>
    <div v-if="!posts.length && !error">
      <p>Loading ......</p>
    </div>
  </div>
 
</template>

<script>

import Posts from '../components/Posts.vue'
import getPosts from '../composables/getPosts'

// @ is an alias to /src
export default {
  name: 'HomeView',
  components: { Posts },
  setup() {

   const {posts, error, load} = getPosts()

   load()

   return { posts, error }
  }
}
</script>
