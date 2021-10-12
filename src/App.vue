<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

</script>

<template>
  <div class="min-h-screen bg-gray-200 text-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="font-blod text-xl pt-2">Menu (DropDown)</h2>
      <div class="mt-4">
        <Menu>
          <MenuButton class="flex items-center bg-blue-500 text-white rounded-md px-4 py-2">        
            <span>More</span>
            <ChevronDownIcon class="h-5 w-5 ml-2" />
          </MenuButton>
          <MenuItems class="absolute bg-white shadow-md rounded-lg flex flex-col focus:outline-none w-56 divide-y divide-gray-100 origin-top-left mt-2">
            <MenuItem v-slot="{ active }">
              <a :class='{ "bg-blue-500": active }' href="/account-settings">
                Account settings
              </a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
              <a :class='{ "bg-blue-500": active }' href="/account-settings">
                Documentation
              </a>
            </MenuItem>
            <MenuItem disabled>
              <span class="opacity-75">Invite a friend (coming soon!)</span>
            </MenuItem>
          </MenuItems>
        </Menu>
      </div>
        
    </div>
  </div>
</template>

<style>

</style>

<script>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";
import { ChevronDownIcon } from '@heroicons/vue/solid'

  export default {
    components: {
      Menu,
      MenuButton,
      MenuItems,
      MenuItem,
      ChevronDownIcon
    },
  };
</script>

