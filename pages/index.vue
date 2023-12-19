
<template>
      <Navbar 
      intent="primary"
      nav="primary">¨
</Navbar>
      <Map/>

      <div>
            <WeatherDisplay :temperature="temperature" />
      </div>

</template>


<script>
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
<style>

</style>