<template>
    <div id="app">
  
      <div class="flex justify-content pt-5 pb-5 bg-gray-100 lg:mt-auto footer">
        <div class="mx-auto w-[900px]">
          <div class="flex py-5 mx-auto justify-center gap-5">
            <img src="../assets/icons/instagram.svg" alt="">
            <img src="../assets/icons/facebook.svg" alt="">
            <img src="../assets/icons/youtube.svg" alt="">
            <img src="../assets/icons/linkedin.svg" alt="">
          </div>
          <div class="flex font-light justify-center mb-3 gap-10 list-none">
            <NuxtLink to="">Domů</NuxtLink>
            <NuxtLink to="">Služby</NuxtLink>
            <NuxtLink to="">O nás</NuxtLink>
            <NuxtLink to="">Náš tým</NuxtLink>
          </div>
          <hr class="border-black">
          <div class="flex justify-center">
            <small class="pt-5 text-gray-500 text-center">Copyright 2024</small>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <style scoped>

    img {
        height: 30px;
    }

  #app {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
  }
  
  .footer {
    margin-top: auto;
  }
  </style>
  