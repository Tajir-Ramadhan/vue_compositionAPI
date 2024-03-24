<template>
  <div class="home">
    <p ref="para">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <hr>
    <button @click="age++">add 1 to age</button>
    <hr>
    <input type="text" v-model="name">
    <hr>
    <div>
      <p>My name is {{ ninja.name }} and my age is {{ ninja.age }}</p>

      <button @click="updateNinja">update ninja</button>
    </div>
  </div>
</template>

<script>
import { ref, reactive } from 'vue'

// @ is an alias to /src
export default {
  name: 'HomeView',
  setup() {
    console.log('setup')
//non reactive variables
    // let name = 'Tajir'
    // let age  = 70

    //reactive variables
    const name = ref('Tajir')
    const age = ref(60)

    const handleClick = () => {
      console.log(para, para.value)
      para.value.classList.add('taji')

      //Updating the refs values
      name.value = 'Don Diego'
      age.value = 70
    }

    const para = ref(null)

    const ninja = reactive({ name: 'Bar Ba Rossa', age: 60})

    const updateNinja = () => {
      ninja.name = "Mama Mzazi"
      ninja.age = 11
    }

    return{
      name,
      age,
      handleClick,
      para,
      ninja,
      updateNinja
    }
  }
}
</script>
