<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

</script>

<template>
  <div class="min-h-screen bg-gray-200 text-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="font-blod text-xl pt-2">Menu (DropDown)</h2>
      <Menu>
        <MenuButton class="flex items-center bg-blue-500 text-white rounded-md px-4 py-2">        
          <span>More</span>
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-2" viewBox="0 0 20 20" fill="currentColor">
              <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
            </svg>
        </MenuButton>
        <MenuItems>
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
</template>

<style>

</style>

<script>
import { Menu, MenuButton, MenuItems, MenuItem } from "@headlessui/vue";

  export default {
    components: {
      Menu,
      MenuButton,
      MenuItems,
      MenuItem,
    },
  };
</script>

