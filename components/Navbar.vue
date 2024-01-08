<template>
    <div :class="navClass" class="z-0" >
        <nav class=" flex justify-between pt-[20px] mx-5">
          <NuxtLink to="/"  class="name ml-5 font-extrabold text-[30px]">ZOOINFO.CZ</NuxtLink>
          <div class="my-auto flex gap-[50px]">
            <Popover class="relative ">
              <PopoverButton :class="btnClass">
                <span>Kam jedete?</span>
                <ChevronDownIcon class="arrow-drop h-5 w-5" aria-hidden="true" />
              </PopoverButton>
              <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1" enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
                <PopoverPanel class="absolute z-10 mt-5 flex w-screen max-w-max -translate-x-1/2 px-4">
                  <div class=" w-[900px] flex-auto overflow-hidden rounded-3xl bg-white text-sm leading-6 shadow-lg ring-1 ring-gray-900/5">
                    <div class="p-4 px-[30px] flex flex-wrap gap-[20px] ">
                      <div v-for="item in regions" :key="item.name" class="py-2 justify-center text-center flex rounded-lg">
                        <div class="w-[180px] px-2">
                          <a :href="item.href" class="s py-3 px-5 rounded-lg  font-semibold text-gray-900 hover:bg-[#F3B664]">
                            {{ item.name }}
                          </a>
                          <p class="mt-1 text-gray-600">{{ item.description }}</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </PopoverPanel>
              </transition>
            </Popover>
          </div>
          <div class="nav-links flex gap-[50px] mr-5">
            <NuxtLink to="/">
              <BaseBtn >
                <span>Kontakt</span>
              </BaseBtn>
            </NuxtLink>
          </div>
        </nav>
    </div>
      <div class="text-[100px] text-white font-bold absolute left-[50%] top-[90px]">
        <div class="relative text-center left-[-50%] w-[1000Px]">
          <slot/>
        </div>
      </div>
</template>

<script setup>
import {computed} from "vue"
import {cva} from "class-variance-authority"

import { Popover, PopoverButton, PopoverPanel } from '@headlessui/vue'
import { ChevronDownIcon} from '@heroicons/vue/20/solid'

const regions = [
  { name: 'Středočeský',  href: '/region/stredocesky-kraj',  },
  { name: 'Hl. město Praha',  href: '/region/hlmesto-praha',  },
  { name: 'Jihočeský', href: '/region/jihocesky-kraj',},
  { name: 'Plzeňský', href: '/region/plzensky-kraj', },
  { name: 'Karlovarský', href: '/region/karlovarsky-kraj', },
  { name: 'Ústecký', href: '/region/ustecky-kraj', },
  { name: 'Liberecký',  href: '/region/liberecky-kraj',  },
  { name: 'Královéhradecký', href: '/region/kralovehradecky-kraj',},
  { name: 'Pardubický', href: '/region/pardubicky-kraj', },
  { name: 'Vysočina', href: '/region/vysocina', },
  { name: 'Jihomoravský', href: '/region/jihomoravsky-kraj', },
  { name: 'Olomoucký', href: '/region/olomoucky-kraj', },
  { name: 'Moravskoslezský', href: '/region/moravskoslezky-kraj', },
  { name: 'Zlínský', href: '/region/zlinsky-kraj', },
]

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
    btn: {
        type: String,
        validator: val => [
          "white",
          "black"
        ].includes(val),
        default: "black"
    },

})


const navClass = computed(() => {
  return cva("px-[100px]", {
    variants: {
      nav: {
        landscape: "nav-picture-1 text-white h-[300px]",
        homepage: "text-white h-[100px]",
        zoo: "text-white h-[300px]",
      },
    },
  })({
    nav: props.nav,
   
  });
});

const btnClass = computed(() => {
  return cva("toggle-button inline-flex  items-center gap-x-1 text-lg font-semibold leading-6 ", {
    variants: {
      btn: {
        white: "text-white",
        black: "text-gray-900",
      },
    },
  })({
    btn: props.btn,
   
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
.zoo-jihlava {
  background-image: url(../assets/images/zoo-jihlava.png);
  
}
.zoo-brno  {
  background-image: url(../assets/images/zoo-brno.jpg);
  background-size:     cover;                   
  background-repeat:   no-repeat;
  background-position: center center;  

}
.nav-picture-4 {
  background-image: url(../assets/images/zoo-praha.jpg);
  background-size:     cover;                   
  background-repeat:   no-repeat;
  background-position: center center;  

}

.name {
  background:
    linear-gradient(
      to right,
      rgb(255, 255, 255),
      rgb(255, 255, 255)
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