<script>
    export default {
        name: 'City',
        props: {
            weatherInfo: {
                type: Object
            },
        }, 
        methods: {
            windDirection(deg) {
                // let deg = weatherInfo?.wind.deg;
                console.log(deg);
                let direction = 0;
                 if(deg == 0) {
                    console.log('Штиль');
                } else if(181 < deg < 360) {
                    console.log('Ветер западный');
                    direction = 1;
                } else if(0<deg<180){
                    console.log('Ветер восточный');
                    direction = 3;
                }
                
                return direction;
            }
        },
    }
</script>

<template>
    <div class="w-4/5 mx-auto rounded-3xl bg-gray-200 p-4 m-6 text-center shadow text-3xl">
        <h1>Weather in {{ weatherInfo?.name }}</h1>
    </div>
    <div class="w-[96%] mx-auto rounded-3xl p-4 mt-6 flex gap-5">
        <div class="w-2/5 rounded-3xl bg-gray-200 p-4">
            <h2 class="text-2xl text-center">Yesterday </h2>
            <div class="hr"></div>
            <p class="text-center mt-8 text-3xl"> {{ weatherInfo?.main.temp }}</p>
            <div class="mt-8 text-xl">
                <p class="flex"><img src="" alt="clouds"><span>Cloudy</span></p>
                <p class="flex"><img src="" alt="wind"><span>North-East</span></p>
                <span>Saturday</span>
            </div>
        </div>
        <div class="w-2/5 rounded-3xl bg-gray-200 p-4">
            <h2 class="text-2xl text-center" @click="windDirection(weatherInfo?.wind.deg)">Today</h2>
            <div class="hr"></div>
            <p class="text-center mt-8 text-3xl">{{ weatherInfo?.main.temp }}</p>
            <div class="mt-8 text-xl">
                <p class="flex"><img :src="`./src/assets/weather-main/${weatherInfo?.weather[0].description}.png`" alt="clouds"><span>{{ weatherInfo?.weather[0].description }}</span></p>
                <p class="flex"><img src="" alt="wind"><span>{{ weatherInfo?.wind.speed }} m/s</span> {{  weatherInfo?.wind.deg }}  </p>
                <span>Saturday</span>
            </div>
        </div>
        <div class="w-2/5 rounded-3xl bg-gray-200 p-4">
            <h2 class="text-2xl text-center">Tomorrow</h2>
            <div class="hr"></div>
            <p class="text-center mt-8 text-3xl">{{ weatherInfo?.main.temp }}</p>
            <div class="mt-8 text-xl">
                <p class="flex"><img src="" alt="clouds"><span>Cloudy</span></p>
                <p class="flex"><img src="" alt="wind"><span>North-East</span></p>
                <span>Saturday</span>
            </div>
        </div>
    </div>
    
</template>
<style scoped>
.hr{
    width: 80%; /* ширина линии */
    height: 1px; /* высота / толщина линии */
    background: #333; /* фон / цвет линии */
    border: 0; /* рамка вокруг разделительной линии (уберем ее) */
    margin: 15px auto 15px auto; /* отступ над и под линией 5 пикселей */
}
</style>