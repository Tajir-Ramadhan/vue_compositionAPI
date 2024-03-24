<template>
  <div class="home">
   <h1>Home</h1>
   <input type="text" v-model="search">
   <p>serch term - {{ search }}</p>

   <div v-for="name in matchingNames" :key="name"> {{ name }}</div>

   <button @click="handleClick">stop watching</button>
  </div>
</template>

<script>
import { ref, reactive,computed, watch, watchEffect } from 'vue'

// @ is an alias to /src
export default {
  name: 'HomeView',
  setup() {
    const search = ref('')
    const names = ref(['mario', 'yoshi', 'Luigi', 'bowser','toad','koopa', 'peach','Tajir'])

    const matchingNames = computed(
      () => {
        return names.value.filter( (name) => name.includes(search.value))
      }
    )

    const stopWatch = watch(search, () => {console.log('Watch function fired')})

    const stopEfect = watchEffect( () => {
      console.log('watch Efect function fired!', search.value)
    })

    const handleClick = () => {
      stopWatch()
      stopEfect()
    }

    return { names, search, matchingNames, handleClick }
  }
}
</script>
