<template>
  <div class="w-full">
    <div class="w-full max-w-md">
      <RadioGroup v-model="selected">
        <RadioGroupLabel class="sr-only">Server size</RadioGroupLabel>
        <div class="space-y-2">
          <RadioGroupOption
            as="template"
            v-for="plan in plans"
            :key="plan.name"
            :value="plan"
            v-slot="{ active, checked }"
          >
            <div
              :class="[
                active
                  ? 'ring-2 ring-offset-2 ring-offset-sky-300 ring-white ring-opacity-60'
                  : '',
                checked ? 'bg-sky-900 bg-opacity-75 text-white ' : 'bg-white ',
              ]"
              class="relative flex px-5 py-4 rounded-lg shadow-md cursor-pointer focus:outline-none"
            >
              <div class="flex items-center justify-between w-full">
                <div class="flex items-center">
                  <div class="text-sm">
                    <RadioGroupLabel
                      as="p"
                      :class="checked ? 'text-white' : 'text-gray-900'"
                      class="font-medium"
                    >
                      {{ plan.name }}
                    </RadioGroupLabel>
                    <RadioGroupDescription
                      as="span"
                      :class="checked ? 'text-sky-100' : 'text-gray-500'"
                      class="inline"
                    >
                      <span> {{ plan.ram }}/{{ plan.cpus }}</span>
                      <span aria-hidden="true"> &middot; </span>
                      <span>{{ plan.disk }}</span>
                    </RadioGroupDescription>
                  </div>
                </div>
                <div v-show="checked" class="flex-shrink-0 text-white">
                  <svg class="w-6 h-6" viewBox="0 0 24 24" fill="none">
                    <circle
                      cx="12"
                      cy="12"
                      r="12"
                      fill="#fff"
                      fill-opacity="0.2"
                    />
                    <path
                      d="M7 13l3 3 7-7"
                      stroke="#fff"
                      stroke-width="1.5"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                </div>
              </div>
            </div>
          </RadioGroupOption>
        </div>
      </RadioGroup>
    </div>
  </div>

   <div class="mt-4">
        <h2 class="font-bold text-xl pt-2">Radio Group</h2>
        <RadioGroup v-model="plan" class="max-w-md mt-8">
          <RadioGroupLabel class="font-bold">Plan</RadioGroupLabel>
          <div class="space-y-4 mt-4">
            <RadioGroupOption v-slot="{ checked }" value="startup" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Startup</div>
                  <div class="text-sm">12GB/6 CPUs &middot; 160GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="business" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Business</div>
                  <div class="text-sm">16GB/8 CPUs &middot; 250GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="enterprise" class="bg-white rounded-md shadow">
              <div
                class="flex items-center justify-between rounded-md px-4 py-4"
                :class="checked ? 'bg-blue-500 text-white' : ''"
              >
                <div>
                  <div class="font-bold">Enterprise</div>
                  <div class="text-sm">32GB/12 CPUs &middot; 500GB SSD disk</div>
                </div>
                <div v-show="checked">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                  </svg>
                </div>
              </div>
            </RadioGroupOption>

          </div>
        </RadioGroup>
      </div>

      <div class="mt-4">
        <h2 class="font-bold text-xl pt-2">Alternate Radio Group</h2>
        <RadioGroup v-model="gameSelection" class="font-retro max-w-md mt-8">
          <RadioGroupLabel class="font-bold">Video Game Menu</RadioGroupLabel>
          <div class="space-y-4 mt-4">
            <RadioGroupOption v-slot="{ checked }" value="new game" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  New Game
                </div>

              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="load game" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  Load Game
                </div>

              </div>
            </RadioGroupOption>

            <RadioGroupOption v-slot="{ checked }" value="settings" class="text-center focus:outline-none cursor-pointer">
              <div
                class="border border-transparent px-4 py-4"
                :class="checked ? 'border-gray-500' : ''"
              >
                <div>
                  Settings
                </div>

              </div>
            </RadioGroupOption>

          </div>
        </RadioGroup>
      </div>
</template>

<script>
import { ref } from 'vue'
import {
  RadioGroup,
  RadioGroupLabel,
  RadioGroupDescription,
  RadioGroupOption,
} from '@headlessui/vue'

const plans = [
  {
    name: 'Startup',
    ram: '12GB',
    cpus: '6 CPUs',
    disk: '160 GB SSD disk',
  },
  {
    name: 'Business',
    ram: '16GB',
    cpus: '8 CPUs',
    disk: '512 GB SSD disk',
  },
  {
    name: 'Enterprise',
    ram: '32GB',
    cpus: '12 CPUs',
    disk: '1024 GB SSD disk',
  },
]

export default {
  components: {
    RadioGroup,
    RadioGroupLabel,
    RadioGroupDescription,
    RadioGroupOption,
  },

  setup() {
    const selected = ref(plans[0])

   const gameSelection= 'new game',

    return { selected, plans, gameSelection }
  },
}
</script>
