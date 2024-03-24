<template>
  <div class="home">
    <p ref="para">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
import { ref } from 'vue'

// @ is an alias to /src
export default {
  name: 'HomeView',
  setup() {
    console.log('setup')

    let name = 'Tajir'
    let age  = 70

    const handleClick = () => {
      console.log(para, para.value)
      para.value.classList.add('taji')
      name = 'Don Diego'
    }

    const para = ref(null)

    return{
      name,
      age,
      handleClick,
      para
    }
  }
}
</script>
