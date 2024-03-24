<template>
  <div class="home">
    <h1>Home</h1>
    <posts :posts="posts"/>
  </div>
 
</template>

<script>
import { ref} from 'vue'
import Posts from '../components/Posts.vue'

// @ is an alias to /src
export default {
  name: 'HomeView',
  components: { Posts },
  setup() {
   const posts = ref([
    {title: 'Welcome to the blog', body: ' Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam nesciunt adipisci illo quis, cupiditate cumque dicta quod perferendis! Temporibus dolorum eaque, ipsam nam minima, nobis velit nisi sunt aperiam reprehenderit ipsa non aliquid ut vitae labore sit corrupti! Ipsum ut sapiente eum consequatur id nostrum reprehenderit, expedita assumenda, soluta veniam tempore deleniti harum asperiores nisi. Repudiandae sapiente ex modi architecto voluptas veritatis sunt. Possimus fugit voluptatum officiis labore, tempore sunt eligendi minima! Maxime laboriosam unde enim corrupti iusto nulla, architecto mollitia rem veniam, itaque distinctio? Facere aliquam sapiente magnam quis commodi libero, omnis eligendi placeat sunt, qui ullam voluptatum architecto.', id: 1},
    {title: 'Top 5 CSS tips', body: 'Lorem ipsum', id: 2},
   ])

   return {
    posts
   }
  }
}
</script>
