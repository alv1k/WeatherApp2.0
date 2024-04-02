<script setup>
import { ref, onMounted } from 'vue';
import { API_KEY, BASE_URL } from './constants';
import Header from './components/Header.vue';
import City from './components/City.vue';
import ExtraInfo from './components/ExtraInfo.vue';

const city = ref('Yakutsk')
const weatherInfo = ref(null)
//console.log("123");

function getWeather() {
  fetch(`${BASE_URL}?q=${city.value}&appid=${API_KEY}&units=metric`)
    .then((response) => response.json())
      .then((data) => weatherInfo.value = data)
}

onMounted(getWeather)

const props = defineProps(['weatherInfo'])


</script>

<template>
  <div class="bg-blue-200 w-3/4 mx-auto itim-regular">
    <!-- <input v-model="city" type="text" class="rounded-3xl border shadow w-1/2 px-6 text-2xl" placeholder="City"> -->
    <!-- <Header :weatherInfo="weatherInfo" :data="data">
    
    </Header> -->

    
    <div id="header" class="w-[96%] mx-auto rounded-3xl bg-gradient-to-r from-green-200 to-purple-300 p-4 flex gap-5">
        <img src="../assets/images/EvaSearchFill.svg" alt="" width="">
        <input @keyup.enter="getWeather" v-model="city" type="text" class="rounded-3xl border shadow w-1/2 px-6 text-2xl" placeholder="City">
        <button class="rounded-3xl bg-gradient-to-l from-green-200 to-purple-300 px-7 py-3 ml-auto text-3xl shadow">My Favorite Cities</button>
    </div>
    <City :weatherInfo="weatherInfo">
      
    </City>
    <ExtraInfo :weatherInfo="weatherInfo">

    </ExtraInfo>
  </div>
  
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');
.itim-regular {
  font-family: "Itim", cursive;
  font-weight: 400;
  font-style: normal;
}


.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
