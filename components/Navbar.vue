<template>
    <div :class="navClass" class="z-0" >
      <nav class=" flex justify-between pt-[20px] mx-5">
        <NuxtLink to="/"  class=" ml-5 font-extrabold text-[30px]">ZOOINFO.CZ</NuxtLink>
        <div class="nav-links flex gap-[50px] mr-5">
          <NuxtLink 
          class="font-bold cursor-pointer text-[20px] my-auto">BLOG</NuxtLink>
          <NuxtLink to="/">
            <BaseBtn intent="primary">
              <span>Kontakt</span>
            </BaseBtn>
          </NuxtLink>
          </div>
        </nav>
      </div>
</template>

<script setup>
import {computed} from "vue"
import {cva} from "class-variance-authority"

const props = defineProps({
    nav: {
        type: String,
        validator: val => ["landscape", "jihlava", "danger", "text"].includes(val),
        default: "landscape"
    },
})


const navClass = computed(() => {
  return cva("px-[100px]", {
    variants: {
      nav: {
        landscape: "nav-picture-1 text-white h-[300px]",
        jihlava: "nav-picture-2 text-white h-[300px]",
        danger: "nav-picture-1",
      },
    },
  })({
    nav: props.nav,
   
  });
});



</script>


<script>

</script>

<style local >

.nav-picture-1 {
  background-image: url(../assets/images/landscape.png);
}
.nav-picture-2 {
  background-image: url(../assets/images/zoo-jihlava.png);
  
}
.nav-picture-3 {
  background-image: url(../assets/images/landscape.png);
}

</style>