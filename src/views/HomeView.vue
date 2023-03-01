<template>
  <div class="home">
    <H1>This is my home page</H1>
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p><br>

    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'HomeView',

  setup(){
    console.log("set up done ..")

    let name = 'Kiboma'
    let age = 31

    const p = ref(null)

    const handleClick = () => {
      console.log(p, p.value)
      p.value.classList.add('test')
      p.value.textContent = 'Hello, text changed'
    }

    return {name, age, handleClick,p}
  }

}
</script>
