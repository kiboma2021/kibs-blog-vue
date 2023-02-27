<template>
  <div class="home">
    <H1>This is my home page</H1>
    <p>My name is {{ name }} and my age is {{ age }}</p>
  </div>
</template>

<script>
export default {
  name: 'HomeView',

  setup(){
    console.log("set up done ..")

    let name = 'Kiboma'
    let age = 31

    return {name, age}
  }

}
</script>
