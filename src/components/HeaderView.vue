<template>
<div class="flex justify-between items-center w-[100%] pt-[45px] pb-[40px] px-[25px] z-50">
    <Menu as="div">
      <div>
        <MenuButton class="justify-center w-full text-white font-medium">
          <MenuIcon class="h-5 w-5" aria-hidden="true" />
        </MenuButton>
      </div>

      <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75" leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
        <MenuItems class="origin-top-right absolute mt-2 w-30 rounded-md bg-[#E5DFA0] focus:outline-none border-2 border-[#8f8b64]">
          <div class="py-1">
            <MenuItem v-slot="{ active }">
              <a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-4 text-sm']"><img class="m-auto" src="src/assets/mastercard_logo.svg"></a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-4 text-sm']"><img class="m-auto" src="src/assets/Buy.svg"></a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-4 text-sm']"><img class="m-auto" src="src/assets/parking.svg"></a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-4 text-[32px]']">🍔</a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <a href="#" :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-4 m-auto']"><img class="m-auto" src="src/assets/beardo_beard_wash_1-removebg-preview 3.png"></a>
            </MenuItem>
          </div>
        </MenuItems>
      </transition>
    </Menu>
    <h1 class="text-[#E5DFA0] text-[18px] font-normal">BRAND BENEFITS</h1>
    <SearchIcon class="h-5 w-5 text-white" aria-hidden="true"/>
</div>
</template>

<script setup>
import { Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { ChevronDownIcon, MenuIcon, SearchIcon} from '@heroicons/vue/solid'
</script>
