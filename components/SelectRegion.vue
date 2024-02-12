<template>
  <Listbox as="div" v-model="selected">
    <div class="relative lg:mt-[0px] sm:pb-[30px] md:mt-[140px] mt-2 flex justify-center">
      <ListboxButton class="relative w-full cursor-default rounded-lg bg-white md:py-[20px] md:px-[30px] py-1.5 pl-3 pr-10 text-left text-gray-900 shadow-sm lg:w-[650px] md:w-[600px] sm:w-[330px] ring-1  md:text-2xl ring-inset ring-gray-300 focus:outline-none focus:ring-2 focus:ring-[--primary] sm:text-sm sm:leading-6">
        <span class="flex items-center">
          <span class="ml-3 block truncate">Vyberte kraj</span>
        </span>
        <span class="pointer-events-none absolute inset-y-0 right-0 ml-3 flex items-center pr-2">
          <ChevronUpDownIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />
        </span>
      </ListboxButton>

      <transition leave-active-class="transition ease-in duration-100" leave-from-class="opacity-100" leave-to-class="opacity-0">
        <ListboxOptions class="absolute z-10 mt-1 md:max-h-[500px] max-h-56 w-full overflow-auto rounded-md bg-white py-1 text-base shadow-lg md:w-[600px] sm:w-[330px] lg:w-[650px] ring-1 ring-black ring-opacity-5 focus:outline-none md:text-xl sm:text-sm">
          <ListboxOption as="template" v-for="region in regions" :key="region.id" :value="region" >
            <li class="text-gray-900 relative cursor-default select-none py-2 pl-3 pr-9">
              <div class="flex items-center">
                <a :href=region.href class="ml-3 block truncate">{{ region.name }}</a>
              </div>

            </li>
          </ListboxOption>
        </ListboxOptions>
      </transition>
    </div>
  </Listbox>
</template>

<script setup>
import { ref } from 'vue'
import { Listbox, ListboxButton, ListboxLabel, ListboxOption, ListboxOptions } from '@headlessui/vue'
import { CheckIcon, ChevronUpDownIcon } from '@heroicons/vue/20/solid'

const regions = [


  {
    id: 1,
    name: 'Hl. Město Praha',
    href: '/region/hlmesto-praha',
  },
  {
    id: 2,
    name: 'Jihočeský kraj',
    href: '/region/jihocesky-kraj',
  },
  {
    id: 3,
    name: 'Jihomoravský kraj',
    href: '/region/jihomoravsky-kraj',
  },
  {
    id: 4,
    name: 'Karlovarský kraj',
    href: '/region/karlovarsky-kraj',
  
  },
  {
    id: 5,
    name: 'Kralovehradský kraj',
    href: '/region/kralovehradsky-kraj',
  
  },
  {
    id: 6,
    name: 'Liberecký kraj',
    href: '/region/liberecky-kraj',  
  },
  {
    id: 7,
    name: 'Moravskoslezký kraj',
    href: '/region/moravskoslezsky-kraj',
  },
  {
    id: 8,
    name: 'Olomoucký kraj',
    href: '/region/olomoucky-kraj',
  },
  {
    id: 9,
    name: 'Pardubický kraj',
    href: '/region/pardubicky-kraj',
  },
  {
    id: 10,
    name: 'Plzeňský kraj',
    href: '/region/plzensky-kraj',
  
  },
  {
    id: 11,
    name: 'Středočeský kraj',
    href: '/region/stredocesky-kraj',
  
  },
  {
    id: 12,
    name: 'Ústecký kraj',
    href: '/region/ustecky-kraj',
  
  },
  {
    id: 13,
    name: 'Vysočina',
    href: '/region/vysocina',
  
  },
  {
    id: 14,
    name: 'Zlínský kraj',
    href: '/region/zlinsky-kraj',
  
  },
  
]

</script>