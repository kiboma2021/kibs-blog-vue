<template>
  <div class="home">
    <H1>This is my home page</H1>
    <p>My name is {{ name }} and my age is {{ age }}</p><br>

    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
export default {
  name: 'HomeView',

  setup(){
    console.log("set up done ..")

    let name = 'Kiboma'
    let age = 31

    const handleClick = () => {
      console.log("Clicked...")
    }

    return {name, age, handleClick}
  }

}
</script>
