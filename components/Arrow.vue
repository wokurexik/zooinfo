<template>
    
    <div :style="{ top: topValue, left: leftValue }" class="point rounded-lg has-tooltip">
        <NuxtLink :to="linkTo">
          <div class="arrow"></div>
          <p class="font-bold mt-2 px-5 text-white text-center">
            <slot name="name"/>
          </p>
          <div class="rounded-bl-lg rounded-br-lg tooltip">
            <p class="text-[15px] mt-3">Hodnocení</p>
            <slot name="star"/>
          </div>
        </NuxtLink>
      </div>
      

</template>

<script setup>
import { defineProps } from 'vue';
  
const props = defineProps(['linkTo', 'topValue', 'leftValue', 'imageUrl']);
</script>