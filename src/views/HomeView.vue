<template>
  <div class="home">
    <H1>This is my home page</H1>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p><br>

    <button @click="handleClick">Click me</button>

    <br> <br>

    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'HomeView',

  setup(){
    console.log("set up done ..")

    const name = ref('Kiboma')
    const age = ref(31)

    const handleClick = () => {
      name.value = "Benard"
      age.value = 47
    }

    return {name, age, handleClick}
  }

}
</script>
