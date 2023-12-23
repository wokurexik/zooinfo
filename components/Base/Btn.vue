<template>


<component :class="buttonClass">
    <slot/>
</component>


</template>

<script setup>
import {computed} from "vue"
import {cva} from "class-variance-authority"

const props = defineProps({
    intent: {
        type: String,
        validator: val => ["primary", "secondary", "danger", "text"].includes(val),
        default: "primary"
    },
    href: {
        type: String,
        default: null
      },
})

const buttonClass = computed(() => {
  return cva("inline-flex items-center justify-center cursor-pointer min-h-[32px] font-bold", {
    variants: {
      intent: {
        primary: "bg-[#F3B664] text-white hover:bg-[#E6A54C] py-2 text-[20px] rounded  px-[30px] ",
        secondary: "text-white bg-[#F3B664] py-3 text-[25px] rounded-lg  px-[50px] ",
        danger: "bg-red-600 text-white hover:bg-red-500",
      },
    },
  })({
    intent: props.intent,
   
  });
});


</script>

