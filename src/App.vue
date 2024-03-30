<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue';
import City from './components/City.vue';
import ExtraInfo from './components/ExtraInfo.vue';
</script>

<template>
  <div class="bg-blue-200 w-3/4 mx-auto itim-regular">
    <Header>
      
    </Header>
    <City>

    </City>
    <ExtraInfo>

    </ExtraInfo>
  </div>
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div> -->
  
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
