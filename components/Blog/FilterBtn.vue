<template>
    <div class="items-center mx-11 flex">
        <Popover class="relative ">
            <PopoverButton class="toggle-button w-[150Px]  inline-flex items-center gap-x-1 text-lg font-semibold leading-6 text-gray-900">
                <span>Kraje</span>
        <ChevronDownIcon class="arrow-drop h-5 w-5" aria-hidden="true" />
      </PopoverButton>
      <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1" enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
        <PopoverPanel class="relative z-10 mt-5 flex w-screen max-w-max px-4">
          <div class="w-[1400Px] flex-auto overflow-hidden bg-white text-sm ">
            <div class="p-4 px-[30px] flex flex-wrap justify-center">
                <div v-for="item in regions" :key="item.name" class="py-2 justify-center text-center flex rounded-lg">
                  <a :href="item.href" class="s py-3 px-5 rounded-lg  font-semibold text-gray-900 hover:bg-[#F3B664]">
                    {{ item.name }}
                  </a>
                  <p class="mt-1 text-gray-600">{{ item.description }}</p>
              </div>
            </div>
          </div>
        </PopoverPanel>
      </transition>
    </Popover>
</div>
</template>

<script setup>
import { Popover, PopoverButton, PopoverPanel } from '@headlessui/vue'
import { ChevronDownIcon} from '@heroicons/vue/20/solid'

const regions = [
  { name: 'Středočeský',  href: '#',  },
  { name: 'Hl. město Praha',  href: '#',  },
  { name: 'Jihočeský', href: '#',},
  { name: 'Plzeňský', href: '#', },
  { name: 'Karlovarský', href: '#', },
  { name: 'Ústecký', href: '#', },
  { name: 'Liberecký',  href: '#',  },
  { name: 'Královéhradecký', href: '#',},
  { name: 'Pardubický', href: '#', },
  { name: 'Vysočina', href: '#', },
  { name: 'Jihomoravský', href: '#', },
  { name: 'Olomoucký', href: '#', },
  { name: 'Moravskoslezský', href: '#', },
  { name: 'Zlínský', href: '#', },
]
</script>

<style>

s:hover {
  color: white;
}

</style>