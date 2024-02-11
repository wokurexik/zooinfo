<template>
  <div>
      <div class="zoo-jihlava">     <!-- :class=route.params.id -->
            <Navbar  nav="zoo" btn="white">{{ info.title }}</Navbar>
        </div>
    <section>
        <hr>
        <div class="lg:flex sm:grid sm:gap-[20px] lg:gap-[100px] sm:px-[20px] justify-center mt-[20px] mb-[100px]">
          <div class="lg:flex sm:grid gap-2 justify-center">
            <div class="my-auto sm:mx-auto">
              <img src="../assets/icons/ticket.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold sm:text-[20px] lg:text-[20px]">Vstupné</p>
              <small class="text-[20px]">{{info.ticketPrice}}</small>
            </div>
          </div>
          <div class="lg:flex sm:grid gap-2 justify-center">
            <div class="my-auto sm:mx-auto">
              <img src="../assets/icons/clock.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold sm:text-[20px] lg:text-[20px]">Otevřené hodiny</p>
              <small class="text-[20px]">{{info.openHours}}</small>
            </div>
          </div>
          <div class="lg:flex sm:grid gap-2 justify-center">
            <div class="my-auto  sm:mx-auto">
              <img src="../assets/icons/cloud.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold sm:text-[20px] lg:text-[20px]">Počasí</p>
              <WeatherDisplay :temperature="temperature" />
            </div>
          </div>
        </div>
        <div class=" lg:mx-auto sm:grid lg:flex max-w-7xl sm:gap-[100px] lg:gap-[200px]">
          <div class="sm:ml-[10px]">
            <h1 class="lg:text-[30px] sm:text-[40px] mb-3 font-bold">Úvod</h1>
            <p class="sm:w-[350px] sm:text-[20px] mb-5 lg:w-[600px]">{{ info.content }}</p>
              
              <a class="underline text-[25px]" target="_blank" :href=info.website>Webové stránky {{ info.title }}</a>
              
              <div class="mt-5">
                <h2 class="text-[30px] font-bold">Hodnocení návštěvníků</h2>
                <p class="text-[30px]">{{ info.reviewStars }}⭐</p>
              </div>  
            </div>

            
            <div class="flex justify-center">
              <iframe class="sm:w-[350px] sm:h-[300px] lg:w-[400px] lg:h-[300px]" :src="info.mapLink"  style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
          </div>

          <div class="lg:flex sm:grid imgs-div flex-wrap gap-3 lg:w-[1000px] mx-auto mt-[200px] justify-center">
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
  import { useRoute, useRouter } from 'vue-router';

  import jsonData from '../../zoo.json';

  const route = useRoute();
  const router = useRouter();
  const info = ref({});
  const temperature = ref(null);

  onMounted(async () => {
    const id = route.params.id;
    info.value = jsonData[id] || jsonData['default'];

    // Check if the info is empty, indicating that the ID was not found
    if (!info.value || !info.value.id) {
      // Redirect to the "Not Found" page or handle it as appropriate
      router.replace('/not-found');
      return;
    }


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
  