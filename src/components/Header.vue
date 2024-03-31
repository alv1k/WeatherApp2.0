<script>
export default {
    name: 'header',
    props: {
        weatherInfo: {
            type: Object
        },
    }
}
</script>
<template>
    
    <div id="header" class="w-[96%] mx-auto rounded-3xl bg-gradient-to-r from-green-200 to-purple-300 p-4 flex gap-5">
        <img src="../assets/images/EvaSearchFill.svg" alt="" width="">
        <input @keyup.enter="getWeather" v-model="city" type="text" class="rounded-3xl border shadow w-1/2 px-6 text-2xl" placeholder="City">
        <button class="rounded-3xl bg-gradient-to-l from-green-200 to-purple-300 px-7 py-3 ml-auto text-3xl shadow">My Favorite Cities</button>
    </div>
</template>