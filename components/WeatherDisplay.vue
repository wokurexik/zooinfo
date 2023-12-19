<template>
    <div>
      <h1>{{ roundedTemperature }}°C</h1>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      temperature: {
        type: Number,
        required: true
      }
    },
    temperature: {
      type: Number,
      required: true
    },
    computed: {
    roundedTemperature() {
      return Math.round(this.temperature);
    }
  }
  }


  
  </script>

