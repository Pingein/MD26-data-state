<script setup lang="ts">
import { onMounted, ref } from 'vue';
import axios from 'axios';
import JokeCard from './JokeCard.vue';

const jokeData = ref([])
const getJokes = async () => {
  return await axios.get('https://v2.jokeapi.dev/joke/Programming?type=single&amount=10').then(({data}) => data)
}

onMounted(async () => {
    getJokes().then(data => jokeData.value = data.jokes)
})
</script>

<template>
  <div class="cards" v-for="joke in jokeData">
    <div class="card">
        <h1 class="category">{{joke.category}}</h1>
        <span>{{joke.joke}}</span>
        <button>+</button>
    </div>
    <!-- <JokeCard category={{joke.category}} joke={{joke.joke}} /> -->
  </div>
</template>

<style scoped>
.cards {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}
.card {
    width: 600px;
    justify-content: space-between;
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
