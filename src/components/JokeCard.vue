<script setup lang="ts">
// import { onMounted, ref } from 'vue';
// import axios from 'axios';

defineProps<{
  category: string,
  joke: string
}>()

// const jokeData = ref([])
// const getJokes = async () => {
//   return await axios.get('https://v2.jokeapi.dev/joke/Programming?type=single&amount=10').then(({data}) => data)
// }

// onMounted(async () => {
//     getJokes().then(data => jokeData.value = data.jokes)
// })
</script>

<template>
  <div class="card">
    <h1 class="category">{{category}}</h1>
    <span>{{joke}}</span>
    <button>+</button>
  </div>
</template>

<style scoped>
.card {
    width: 200px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    background-color: hsla(160, 100%, 37%, 1);
    color: #181818;
    gap: 5px;
    border-radius: 5px;
}
.category {
    line-height: 1;
}

</style>
