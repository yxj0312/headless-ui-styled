<script setup>
import Modal from './components/Modal.vue';
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
</script>

<template>
  <div class="min-h-screen bg-gray-200 text-gray-900">
    <div class="container mx-auto px-4">
      <h2 class="font-bold text-xl pt-2">Menu (DropDown)</h2>
      <div class="mt-4">
        <Menu>
          <MenuButton class="flex items-center bg-blue-500 text-white rounded-md px-4 py-2">
            <span>More</span>
            <ChevronDownIcon class="h-5 w-5 ml-2" />
          </MenuButton>
          <transition
            enter-active-class="transition duration-200 ease-out"
            enter-from-class="transform scale-75 opacity-0"
            enter-to-class="transform scale-100 opacity-100"
            leave-active-class="transition duration-100 ease-out"
            leave-from-class="transform scale-100 opacity-100"
            leave-to-class="transform scale-75 opacity-0"
          >
            <MenuItems
              class="absolute bg-white shadow-md rounded-lg flex flex-col focus:outline-none w-56 divide-y divide-gray-100 origin-top-left mt-2"
            >
              <div class="px-1 py-1">
                <MenuItem v-slot="{ active }">
                  <button
                    class="w-full flex items-center rounded-md px-2 py-2"
                    :class="{ 'bg-blue-500 text-white': active }"
                  >
                    <PencilIcon class="h-4 w-4" />
                    <span class="ml-2">Edit</span>
                  </button>
                </MenuItem>
                <MenuItem v-slot="{ active }">
                  <button
                    class="w-full flex items-center rounded-md px-2 py-2"
                    :class="{ 'bg-blue-500 text-white': active }"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z"
                      />
                    </svg>
                    <span class="ml-2">Duplicate</span>
                  </button>
                </MenuItem>
              </div>

              <div class="px-1 py-1">
                <MenuItem v-slot="{ active }">
                  <button
                    class="w-full flex items-center rounded-md px-2 py-2"
                    :class="{ 'bg-blue-500 text-white': active }"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M5 8h14M5 8a2 2 0 110-4h14a2 2 0 110 4M5 8v10a2 2 0 002 2h10a2 2 0 002-2V8m-9 4h4"
                      />
                    </svg>
                    <span class="ml-2">Archive</span>
                  </button>
                </MenuItem>

                <div class="px-1 py-1">
                  <MenuItem v-slot="{ active }">
                    <button
                      class="w-full flex items-center rounded-md px-2 py-2"
                      :class="{ 'bg-blue-500 text-white': active }"
                    >
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-4 w-4"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M7 11.5V14m0-2.5v-6a1.5 1.5 0 113 0m-3 6a1.5 1.5 0 00-3 0v2a7.5 7.5 0 0015 0v-5a1.5 1.5 0 00-3 0m-6-3V11m0-5.5v-1a1.5 1.5 0 013 0v1m0 0V11m0-5.5a1.5 1.5 0 013 0v3m0 0V11"
                        />
                      </svg>
                      <span class="ml-2">Move</span>
                    </button>
                  </MenuItem>
                </div>
              </div>

              <div class="px-1 py-1">
                <MenuItem v-slot="{ active, disabled }" disabled>
                  <button
                    class="w-full flex items-center rounded-md px-2 py-2"
                    :class="{
                      'bg-blue-500 text-white': active,
                      'opacity-50 cursor-not-allowed': disabled,
                    }"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"
                      />
                    </svg>
                    <span class="ml-2">Destroy</span>
                  </button>
                </MenuItem>
                <MenuItem v-slot="{ active }">
                  <button
                    class="w-full flex items-center rounded-md px-2 py-2"
                    :class="{ 'bg-blue-500 text-white': active }"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="h-4 w-4"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z"
                      />
                    </svg>
                    <span class="ml-2">Delete</span>
                  </button>
                </MenuItem>
              </div>
            </MenuItems>
          </transition>
        </Menu>

        <div
          class="mt-4"
        >Lorem ipsum dolor sit, amet consectetur adipisicing elit. Modi, aliquid. Cumque atque quidem similique ducimus nulla sit dolore soluta. Doloribus vitae et maiores aliquid dignissimos velit odit aut ab assumenda!</div>

        <div class="mt-4">
          <h2 class="font-bold text-xl pt-2">Dialog (Modal)</h2>
          <div class="mt-4">
            <testModal />
          </div>
        </div>

        <div class="mt-4">
          <h2 class="font-bold text-xl pt-2">Radio Group</h2>
          <div class="mt-4">
            <radioGroup />
          </div>
        </div>

        <div class="mt-4">
          <h2 class="font-bold text-xl pt-2">Tabs</h2>
          <div class="mt-4">
            <tabs />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import {
  Menu, MenuButton, MenuItems, MenuItem, TransitionRoot, TransitionChild, Dialog, DialogOverlay, DialogTitle,
} from "@headlessui/vue";
import { ChevronDownIcon } from "@heroicons/vue/solid";
import { PencilIcon } from "@heroicons/vue/outline";
import testModal from './components/Modal.vue';
import radioGroup from './components/RadioButton.vue'
import tabs from './components/Tabs.vue'
export default {
  components: {
    Menu,
    MenuButton,
    MenuItems,
    MenuItem,
    TransitionRoot,
    TransitionChild,
    Dialog,
    DialogOverlay,
    DialogTitle,
    ChevronDownIcon,
    PencilIcon,
    Modal
  },

  setup() {
    const isOpen = ref(true)

    return {
      isOpen,
      closeModal() {
        isOpen.value = false
      },
      openModal() {
        isOpen.value = true
      },
    }
  },
};
</script>
