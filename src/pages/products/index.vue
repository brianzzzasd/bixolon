<script setup>
import { ref } from 'vue'
import {
  Dialog,
  DialogPanel,
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  TransitionChild,
  TransitionRoot,
} from '@headlessui/vue'
import { XMarkIcon } from '@heroicons/vue/24/outline'
import { ChevronDownIcon, PlusIcon } from '@heroicons/vue/20/solid'

const products = [
  {
    id: 1,
    name: 'SRP-S3000',
    description_1: '3-inch Linerless Printer',
    description_2: 'Feature-Rich',
    description_3: 'Premium',
    href: '/products/1',
    imageSrc: '/printer_1.jpeg',
  },
  {
    id: 2,
    name: 'SRP-S300',
    description_1: '3 inch Re-Stick',
    description_2: 'Label and Receipt',
    description_3: 'Direct Thermal Printer',
    href: '/products/2',
    imageSrc: '/printer_2.jpeg',
  },
  {
    id: 3,
    name: 'SRP-S200',
    description_1: '2-inch Direct Thermal',
    description_2: 'Linerless Printer',
    description_3: 'Compact and Economical',
    href: '/products/3',
    imageSrc: '/printer_3.jpeg',
  },
  {
    id: 4,
    name: 'SRP-Q300',
    description_1: 'Smart and Flexible',
    description_2: '3 inch Cube',
    description_3: 'Printer for mPOS',
    href: '/products/4',
    imageSrc: '/printer_4.jpeg',
  },
  {
    id: 5,
    name: 'SRP-S320',
    description_1: '3-inch',
    description_2: 'Linerless and Receipt',
    description_3: 'Ideal for use with electronic scales',
    href: '/products/5',
    imageSrc: '/printer_5.jpeg',
  },
  {
    id: 6,
    name: 'SRP-Q200',
    description_1: 'Ultra Compact',
    description_2: '2-inch Cube',
    description_3: 'Direct Thermal Printer',
    href: '/products/6',
    imageSrc: '/printer_6.jpeg',
  },
  {
    id: 7,
    name: 'SRP-350plusIII',
    description_1: 'The perfect fit for mPOS solutions',
    description_2: '3 inch Thermal',
    description_3: 'mPOS-ible Receipt Printer',
    href: '/products/7',
    imageSrc: '/printer_7.jpeg',
  },
  {
    id: 8,
    name: 'SRP-350III',
    description_1: 'The industry’s steady seller',
    description_2: '3 inch Thermal',
    description_3: 'Receipt Printer',
    href: '/products/8',
    imageSrc: '/printer_8.jpeg',
  },
]

const filters = [
  {
    id: 'printers',
    name: 'Printers',
    options: [
      { value: 'pos', label: 'POS' },
      { value: 'label', label: 'Label' },
      { value: 'linerless', label: 'Linerless' },
      { value: 'soho', label: 'SOHO' },
      { value: 'mobile', label: 'Mobile' },
      { value: 'kiosk', label: 'Kiosk' },
    ],
  },
  {
    id: 'accesories',
    name: 'Accessories',
    options: [
      { value: 'covers', label: 'Covers' },
      { value: 'stands', label: 'Stands' },
      { value: 'mounts', label: 'Mounts' },
      { value: 'charging', label: 'Charging' },
      { value: 'clips', label: 'Clips' },
      { value: 'others', label: 'Others' },
    ],
  },
]

const mobileFiltersOpen = ref(false)
</script>

<template>
  <div class="bg-white">
    <div>
      <!-- Mobile filter dialog -->
      <TransitionRoot as="template" :show="mobileFiltersOpen">
        <Dialog as="div" class="relative z-40 lg:hidden" @close="mobileFiltersOpen = false">
          <TransitionChild as="template" enter="transition-opacity ease-linear duration-300" enter-from="opacity-0" enter-to="opacity-100" leave="transition-opacity ease-linear duration-300" leave-from="opacity-100" leave-to="opacity-0">
            <div class="fixed inset-0 bg-black bg-opacity-25" />
          </TransitionChild>

          <div class="fixed inset-0 z-40 flex">
            <TransitionChild as="template" enter="transition ease-in-out duration-300 transform" enter-from="translate-x-full" enter-to="translate-x-0" leave="transition ease-in-out duration-300 transform" leave-from="translate-x-0" leave-to="translate-x-full">
              <DialogPanel class="relative ml-auto flex h-full w-full max-w-xs flex-col overflow-y-auto bg-white py-4 pb-6 shadow-xl">
                <div class="flex items-center justify-between px-4">
                  <h2 class="text-lg font-medium text-gray-900">
                    Filters
                  </h2>
                  <button type="button" class="-mr-2 flex h-10 w-10 items-center justify-center p-2 text-gray-400 hover:text-gray-500" @click="mobileFiltersOpen = false">
                    <span class="sr-only">Close menu</span>
                    <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                  </button>
                </div>

                <!-- Filters -->
                <form class="mt-4">
                  <Disclosure v-for="section in filters" :key="section.name" v-slot="{ open }" as="div" class="border-t border-gray-200 pt-4 pb-4">
                    <fieldset>
                      <legend class="w-full px-2">
                        <DisclosureButton class="flex w-full items-center justify-between p-2 text-gray-400 hover:text-gray-500">
                          <span class="text-sm font-medium text-gray-900">{{ section.name }}</span>
                          <span class="ml-6 flex h-7 items-center">
                            <ChevronDownIcon class="h-5 w-5 transform" :class="[open ? '-rotate-180' : 'rotate-0']" aria-hidden="true" />
                          </span>
                        </DisclosureButton>
                      </legend>
                      <DisclosurePanel class="px-4 pt-4 pb-2">
                        <div class="space-y-6">
                          <div v-for="(option, optionIdx) in section.options" :key="option.value" class="flex items-center">
                            <input :id="`${section.id}-${optionIdx}-mobile`" :name="`${section.id}[]`" :value="option.value" type="checkbox" class="h-4 w-4 rounded border-gray-300 text-orange-600 focus:ring-orange-500">
                            <label :for="`${section.id}-${optionIdx}-mobile`" class="ml-3 text-sm text-gray-500">{{ option.label }}</label>
                          </div>
                        </div>
                      </DisclosurePanel>
                    </fieldset>
                  </Disclosure>
                </form>
              </DialogPanel>
            </TransitionChild>
          </div>
        </Dialog>
      </TransitionRoot>

      <main class="mx-auto max-w-2xl py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
        <div class="border-b border-gray-200 pb-10">
          <h1 class="text-4xl font-bold tracking-tight text-gray-900">
            Products
          </h1>
          <p class="mt-4 text-base text-gray-500">
            Explore our products that make us a leading global Mobile, Label and POS printer manufacturer.
          </p>
        </div>

        <div class="pt-12 lg:grid lg:grid-cols-3 lg:gap-x-8 xl:grid-cols-4">
          <aside>
            <h2 class="sr-only">
              Filters
            </h2>

            <button type="button" class="inline-flex items-center lg:hidden" @click="mobileFiltersOpen = true">
              <span class="text-sm font-medium text-gray-700">Filters</span>
              <PlusIcon class="ml-1 h-5 w-5 flex-shrink-0 text-gray-400" aria-hidden="true" />
            </button>

            <div class="hidden lg:block">
              <form class="space-y-10 divide-y divide-gray-200">
                <div v-for="(section, sectionIdx) in filters" :key="section.name" :class="sectionIdx === 0 ? null : 'pt-10'">
                  <fieldset>
                    <legend class="block text-sm font-medium text-gray-900">
                      {{ section.name }}
                    </legend>
                    <div class="space-y-3 pt-6">
                      <div v-for="(option, optionIdx) in section.options" :key="option.value" class="flex items-center">
                        <input :id="`${section.id}-${optionIdx}`" :name="`${section.id}[]`" :value="option.value" type="checkbox" class="h-4 w-4 rounded border-gray-300 text-orange-600 focus:ring-orange-500">
                        <label :for="`${section.id}-${optionIdx}`" class="ml-3 text-sm text-gray-600">{{ option.label }}</label>
                      </div>
                    </div>
                  </fieldset>
                </div>
              </form>
            </div>
          </aside>

          <!-- Product grid -->
          <div class="mt-6 lg:col-span-2 lg:mt-0 xl:col-span-3">
            <div class="bg-white">
              <div class="mx-auto max-w-2xl py-5 px-4 sm:py-10 sm:px-6 lg:max-w-7xl lg:px-8">
                <h2 class="text-2xl font-bold tracking-tight text-gray-900">
                  Printers
                </h2>

                <div class="mt-6 grid grid-cols-1 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-3 xl:gap-x-8">
                  <div v-for="product in products" :key="product.id" class="group relative">
                    <div class="aspect-w-1 aspect-h-1 w-full overflow-hidden rounded-md bg-gray-200 group-hover:opacity-75 lg:aspect-none">
                      <img class="min-h-50 border border-gray-200" :src="product.imageSrc" width="500" height="auto">
                    </div>
                    <div class="mt-4 flex justify-between">
                      <div>
                        <h3 class="text-sm text-gray-700">
                          <a :href="product.href">
                            <span aria-hidden="true" class="absolute inset-0" />
                            {{ product.name }}
                          </a>
                        </h3>
                        <p class="mt-1 text-sm text-gray-500">
                          {{ product.description_1 }}
                        </p>
                        <p class="mt-1 text-sm text-gray-500">
                          {{ product.description_2 }}
                        </p>
                        <p class="mt-1 text-sm text-gray-500">
                          {{ product.description_3 }}
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
</template>
