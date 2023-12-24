<template>
    <Navbar 
      intent="primary"
      nav="jihlava">
        Jihlava
    </Navbar>
    <section>
        <hr>
        <div class="flex gap-[50px] justify-center mt-[20px] mb-[100px]">
          <div class="flex gap-2">
            <div class="my-auto">
              <img src="../../assets/icons/clock.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold text-[20px]">Otevřené hodiny</p>
              <small class="text-[17px]">9:00 - 16:00</small>
            </div>
          </div>
          <div class="flex gap-2">
            <div class="my-auto">
              <img src="../../assets/icons/ticket.svg" alt="">
            </div>
            <div class="text-center">
              <p class="font-bold text-[20px]">Vstupné</p>
              <small class="text-[17px]">150 Kč / 100 Kč</small>
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
            <p class=" mb-5 w-[600px]">V údolí říčky Jihlávky leží Zoo Jihlava, která je domovem více než 200 druhů zvířat. 
              V posledních letech zoologická zahrada prochází velkým vývojem a postavila několik nových pavilonů. 
              Zoo je známá tím, že chová perské levharty, které mají v České republice pouze v Zoo Dvůr Králové.</p>
              
              <a class="underline" href="">Webové stránky Zoologické zahrady Jihlava</a>
              
              <div class="mt-5">
                <h2 class="text-[30px] font-bold">Hodnocení návštěvníků</h2>
                <img class="w-[150px]" src="../../assets/regions/stars/four.svg" alt="">
              </div>
            </div>
            <div>
              <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d81866.24621303468!2d14.336171150207495!3d50.117730085983816!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x470bead4f9db039b%3A0x96d9543c02ebb5bd!2sZoo%20Praha!5e0!3m2!1scs!2scz!4v1702335949034!5m2!1scs!2scz" width="400" height="300" style="border:0;" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
          </div>
          
          <div class="text-3xl font-bold text-center mt-[100px]">
            <h2>Novinky ze Zoo Jihlava</h2>
          </div>
          <div class=" mt-11">
            <BlogPostLatest :path="'/posts/vysocina/zoo-jihlava'"/>
          </div>          
        </section>
      </template>


<script >
import axios from 'axios';


export default {
  data() {
    return {
      temperature: null
    };
  },
  async mounted() {
    try {
      const response = await axios.get(
        'https://api.openweathermap.org/data/2.5/weather?q=Brno&appid=0518746354b04b148bc704380b98c474&units=metric'
      );
      this.temperature = response.data.main.temp;
    } catch (error) {
      console.error('Error fetching weather data:', error);
    }
  }
};

</script>

