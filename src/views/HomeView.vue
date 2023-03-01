<template>
  <div class="home">
    <h1>This is my home page</h1>
    <p ref="p">My name is {{ Kibs.name }} and my age is {{ Kibs.age }}</p><br>

    <h3>Reactive</h3>
    <p>{{ kibs2.name }} - {{ kibs2.age }}</p>

    <button @click="handleClick">Click me</button> <br>
    <button @click="updateKibs2">Update kibs 2</button>

    <br> <br>

    <input type="text" v-model="Kibs.name">

    <br> <br> <br>
    <hr>
    <input type="text" v-model="search">
    <p>Search: {{ search }}</p>

    <div v-for="name in matchingNames" :key="name">{{ name }}</div>
  </div>
</template>

<script>
import { computed, reactive, ref } from 'vue'
export default {
  name: 'HomeView',

  setup(){
    const Kibs = ref({name: 'Kiboma', age: '31'})
    const kibs2 = reactive({name: 'lagos', age: '65'})
  
    const handleClick = () => {
      Kibs.value.name = "Benard"
      Kibs.value.age = 47
    }

    const updateKibs2 = () => {
      kibs2.name = "Lagos Naigeria"
      kibs2.age = 100
    }
    const search = ref('')
    const names = ref(['Esther', 'Jane', 'Marion', 'Brian', 'James', 'Amos'])

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value))
    })

    return {Kibs, handleClick, kibs2, updateKibs2, names, search, matchingNames}
  }

}
</script>
