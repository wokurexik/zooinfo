<template>
    <div>
        <div :class=route.params.id>
            <Navbar  nav="zoo" btn="white">{{ info.title }}</Navbar>
        </div>
    <section>
        <hr>
        <div class="flex gap-[50px] justify-center mt-[20px] mb-[100px]">
          <div class="flex gap-2">
            <div class="my-auto">
              <img src="../../assets/icons/clock.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold text-[20px]">Otevřené hodiny</p>
              <small class="text-[17px]">{{info.openHours}}</small>
            </div>
          </div>
          <div class="flex gap-2">
            <div class="my-auto">
              <img src="../../assets/icons/ticket.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold text-[20px]">Vstupné</p>
              <small class="text-[17px]">{{info.ticketPrice}}</small>
            </div>
          </div>
          <div class="flex gap-2">
            <div class="my-auto">
              <img src="../../assets/icons/cloud.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold text-[20px]">Počasí</p>
              <WeatherDisplay :temperature="temperature" />
            </div>
          </div>
        </div>
        <div class="mx-auto flex max-w-7xl gap-[200px]">
          <div class="">
            <h1 class="text-[30px] mb-3 font-bold">Úvod</h1>
            <p class=" mb-5 w-[600px]">{{ info.content }}</p>
              
              <a class="underline" :href=info.website>Webové stránky Zoologické zahrady Jihlava</a>
              
              <div class="mt-5">
                <h2 class="text-[30px] font-bold">Hodnocení návštěvníků</h2>
                <p class="text-[30px]">{{ info.reviewStars }}⭐</p>
              </div>  
            </div>

            
            <div>
              <iframe :src="info.mapLink" width="400" height="300" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
          </div>

          <div v-if="info.component === 'Navbar'">
            <Navbar :nav="info.nav" :btn="info.btn" />
          </div>


          <div class="flex imgs-div flex-wrap gap-3 w-[1000px] mx-auto mt-[200px] justify-center">
             <img v-for="(img, index) in info.images" :key="index" class="w-[300px] h-[300px] object-cover" :src="img" alt="">
          </div>

        </section>
    </div>
  
    <Head>
      <Title>{{ info.title }}</Title>
    </Head>
  
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue';
  import axios from 'axios';
  import { useRoute } from 'vue-router';
  
  import jsonData from '../../zoo.json';
  
  const route = useRoute();
  const info = ref({});
  const temperature = ref(null);
  
  onMounted(async () => {
    const id = route.params.id;
    info.value = jsonData[id] || jsonData['default'];
  
    try {
      const response = await axios.get(
        `https://api.openweathermap.org/data/2.5/weather?q=${info.value.city}&appid=0518746354b04b148bc704380b98c474&units=metric`
      );
      temperature.value = response.data.main.temp;
    } catch (error) {
      console.error('Error fetching weather data:', error);
    }
  });
  </script>
  