<template>
    <div>
        <div class="nav-picture-2">
    <Navbar 
    nav="zoo" 
    btn="white">
   {{ info.title }}
  </Navbar>
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
              
              <a class="underline" href="">Webové stránky Zoologické zahrady Jihlava</a>
              
              <div class="mt-5">
                <h2 class="text-[30px] font-bold">Hodnocení návštěvníků</h2>
                <p class="text-[30px]">{{ info.reviewStars }}⭐</p>
              </div>
            </div>
            <div>
              <iframe :src="info.mapLink" width="400" height="300" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
          </div>
          <div class="flex flex-wrap ">
          </div>
        </section>
    </div>
  
    <Head>
      <Title>{{ info.title }}</Title>
      <Meta
        name="description"
        content="Build your next Vue.js application with confidence using Nuxt...."
      />
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
  