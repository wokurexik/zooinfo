<template>
    <div class=" justify-center mt-11 flex-wrap bg-gray-200 gap-5 flex rounded-lg ">
      <div v-for="item in regions" :key="item.name" class="py-2 justify-center text-center flex rounded-lg">
          <a :href="item.href" class="py-3 px-5 rounded-lg text-sm font-semibold shadow-sm bg-white text-gray-900 hover:bg-[#F3B664]">
            {{ item.name }}
          </a>
          <p class="mt-1 text-gray-600">{{ item.description }}</p>
      </div>
</div>
</template>

<script setup>

    const regions = [
      { name: 'Středočeský',  href: '/blog/stredocesky-kraj',  },
      { name: 'Hl. město Praha',  href: '/blog/hlmesto-praha',  },
      { name: 'Jihočeský', href: '/blog/jihocesky-kraj',},
      { name: 'Plzeňský', href: '/blog/plzensky-kraj', },
      { name: 'Karlovarský', href: '/blog/kralovarsky-kraj', },
      { name: 'Ústecký', href: '/blog/ustecky-kraj', },
      { name: 'Liberecký',  href: '/blog/liberecky-kraj',  },
      { name: 'Královéhradecký', href: '/blog/kralovehradecky-kraj',},
      { name: 'Pardubický', href: '/blog/pardubicky-kraj', },
      { name: 'Vysočina', href: '/blog/vysocina', },
      { name: 'Jihomoravský', href: '/blog/jihomoravsky-kraj', },
      { name: 'Olomoucký', href: '/blog/olomoucky-kraj', },
      { name: 'Moravskoslezský', href: '/blog/moravskoslezsky-kraj', },
      { name: 'Zlínský', href: '/blog/zlinsky-kraj', },
    ]
    </script>

<style>





</style>