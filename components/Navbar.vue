<template>
    <div :class="navClass" class="z-0" >
      <nav class=" flex justify-between pt-[20px] mx-5">
        <NuxtLink to="/"  class="name ml-5 font-extrabold text-[30px]">ZOOINFO.CZ</NuxtLink>
        <div class="my-auto flex gap-[50px]">
          <RegionMenu/>
          <!-- <RegionMenu/> -->
        </div>
        <div class="nav-links flex gap-[50px] mr-5">
          <NuxtLink 
          to="/blog" class="font-bold cursor-pointer text-[20px] my-auto">BLOG</NuxtLink>
          <NuxtLink to="/">
            <BaseBtn intent="primary">
              <span>Kontakt</span>
            </BaseBtn>
          </NuxtLink>
          </div>
        </nav>
      </div>
      <div class="text-[100px] text-white font-bold absolute left-[40%]  top-[90px]">
        <slot/>
      </div>
</template>

<script setup>
import {computed} from "vue"
import {cva} from "class-variance-authority"


const props = defineProps({
    nav: {
        type: String,
        validator: val => [
          "landscape", 
          "jihlava", 
          "brno", 
          "text"
        ].includes(val),
        default: "landscape"
    },
})


const navClass = computed(() => {
  return cva("px-[100px]", {
    variants: {
      nav: {
        landscape: "nav-picture-1 text-white h-[300px]",
        jihlava: "nav-picture-2 text-white  h-[300px]",
        brno: "text-white h-[300px]",
      },
    },
  })({
    nav: props.nav,
   
  });
});

</script>

<script>

export default {
    data() {
      return {
        showNavbar: false,
      };
    },
    methods: {
      toggleNavbar() {
        this.showNavbar = !this.showNavbar;
      },
    },
  };

</script>


<style>

.nav-picture-1 {
  background-image: url(../assets/images/landscape.png);
}
.nav-picture-2 {
  background-image: url(../assets/images/zoo-jihlava.png);
  
}
.nav-picture-3 {
  background-image: url(../assets/images/zoo-brno.jpg);
  background-size:     cover;                   
  background-repeat:   no-repeat;
  background-position: center center;  

}

.name{
  background:
    linear-gradient(
      to right,
      black,
      black
    ),
    linear-gradient(
      to right,
      #F3B664,
      #F3B664,
      #F3B664
  );
  background-size: 100% 3px, 0 3px;
  background-position: 100% 100%, 0 100%;
  background-repeat: no-repeat;
  transition: background-size 400ms;
}

.name:hover {
  background-size: 0 3px, 100% 3px;
}

</style>