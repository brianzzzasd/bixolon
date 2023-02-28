<script setup>
import { computed, ref } from 'vue'
import {
  Combobox,
  ComboboxButton,
  ComboboxInput,
  ComboboxLabel,
  ComboboxOption,
  ComboboxOptions,
  Dialog,
  DialogPanel,
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
  Popover,
  PopoverButton,
  PopoverGroup,
  PopoverPanel,

  Tab, TabGroup, TabList, TabPanel, TabPanels, TransitionChild, TransitionRoot,
} from '@headlessui/vue'
import { Bars3Icon, BellIcon, MagnifyingGlassIcon, ShoppingBagIcon, ShoppingCartIcon, UserIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import { CheckIcon, ChevronDownIcon, ChevronUpDownIcon } from '@heroicons/vue/20/solid'
const people = [
  {
    id: 1,
    name: 'Leslie Alexander',
    imageUrl:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
  },
  {
    id: 2,
    name: 'Alexander Leslie ',
    imageUrl:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
  },
]

const query = ref('')
const selectedPerson = ref(null)
const filteredPeople = computed(() =>
  query.value === ''
    ? people
    : people.filter((person) => {
      return person.name.toLowerCase().includes(query.value.toLowerCase())
    }),
)

const currencies = ['CAD', 'USD', 'AUD', 'EUR', 'GBP']
const navigation = {
  categories: [
    {
      id: 'products_featured',
      name: 'Products',
      featured: [
        {
          name: 'New Arrivals',
          href: '/products',
          imageSrc: '/kiosk_printer.png',
          imageAlt: 'Models sitting back to back, wearing Basic Tee in black and bone.',
        },
        // {
        //   name: 'Label Printers',
        //   href: '/products',
        //   imageSrc: '/label_printer.png',
        //   imageAlt: 'Close up of Basic Tee fall bundle with off-white, ochre, olive, and black tees.',
        // },
        // {
        //   name: 'POS Printers',
        //   href: '/products',
        //   imageSrc: '/printer_1.jpeg',
        //   imageAlt: 'Model wearing minimalist watch with black wristband and white watch face.',
        // },
      ],
      sections: [
        [
          {
            id: 'products',
            name: 'Products',
            items: [
              { name: 'Label Printers', href: '#' },
              { name: 'Linerless Printers', href: '#' },
              { name: 'SOHO Series', href: '#' },
              { name: 'Mobile Printers', href: '#' },
              { name: 'Kiosk Printers', href: '#' },
            ],
          },
        ],
        [
          {
            id: 'collection',
            name: 'Shop Collection',
            items: [
              { name: 'POS Printers', href: '#' },
              { name: 'POS Peripherals', href: '#' },
            ],
          },
        ],
        [
          {
            id: 'collection',
            name: 'Shop Collection',
            items: [
              { name: 'Accessories', href: '#' },
            ],
          },
        ],
      ],
    },
    {
      id: 'products_featured',
      name: 'Solutions',
      featured: [
        {
          name: 'New Arrivals',
          href: '#',
          imageSrc: '/kiosk_printer.png',
          imageAlt: 'Models sitting back to back, wearing Basic Tee in black and bone.',
        },
        {
          name: 'Label Printers',
          href: '#',
          imageSrc: '/label_printer.png',
          imageAlt: 'Close up of Basic Tee fall bundle with off-white, ochre, olive, and black tees.',
        },
        {
          name: 'POS Printers',
          href: '#',
          imageSrc: '/printer_1.jpeg',
          imageAlt: 'Model wearing minimalist watch with black wristband and white watch face.',
        },
      ],
      sections: [
        [
          {
            id: 'shoes',
            name: 'Shoes & Accessories',
            items: [
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
            ],
          },
          {
            id: 'collection',
            name: 'Shop Collection',
            items: [
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
            ],
          },
        ],
        [
          {
            id: 'clothing',
            name: 'All Clothing',
            items: [
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
            ],
          },
          {
            id: 'accessories',
            name: 'All Accessories',
            items: [
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
            ],
          },
        ],
        [
          {
            id: 'brands',
            name: 'Brands',
            items: [
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
              { name: 'Solution', href: '#' },
            ],
          },
        ],
      ],
    },
  ],
  pages: [
    { name: 'Company', href: '#' },
    { name: 'Unite Program Partner', href: '#' },
    { name: 'About', href: '#' },
  ],
}

const collections = [
  {
    name: 'SRP-S300',
    description: 'Direct Thermal Printer',
    imageSrc: '/public/printer_1.jpeg',
    imageAlt: 'Desk with leather desk pad, walnut desk organizer, wireless keyboard and mouse, and porcelain mug.',
    href: '#',
  },
  {
    name: 'SRP-270',
    description: 'Receipt Printer',
    imageSrc: '/public/printer_2.jpeg',
    imageAlt: 'Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant.',
    href: '#',
  },
  {
    name: 'STP-103III',
    description: 'POS Printer',
    imageSrc: '/public/printer_3.jpeg',
    imageAlt: 'Collection of four insulated travel bottles on wooden shelf.',
    href: '#',
  },
]
const testimonials = [
  {
    id: 1,
    quote:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    attribution: 'Sarah Peters, New Orleans',
  },
  {
    id: 2,
    quote:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    attribution: 'Kelly McPherson, Chicago',
  },
  {
    id: 3,
    quote:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    attribution: 'Chris Paul, Phoenix',
  },
]

const mobileMenuOpen = ref(false)
</script>

<template>
  <div>
    <!-- Mobile menu -->
    <TransitionRoot as="template" :show="mobileMenuOpen">
      <Dialog as="div" class="relative z-40 lg:hidden" @close="mobileMenuOpen = false">
        <TransitionChild as="template" enter="transition-opacity ease-linear duration-300" enter-from="opacity-0" enter-to="opacity-100" leave="transition-opacity ease-linear duration-300" leave-from="opacity-100" leave-to="opacity-0">
          <div class="fixed inset-0 bg-black bg-opacity-25" />
        </TransitionChild>

        <div class="fixed inset-0 z-40 flex">
          <TransitionChild as="template" enter="transition ease-in-out duration-300 transform" enter-from="-translate-x-full" enter-to="translate-x-0" leave="transition ease-in-out duration-300 transform" leave-from="translate-x-0" leave-to="-translate-x-full">
            <DialogPanel class="relative flex w-full max-w-xs flex-col overflow-y-auto bg-white pb-12 shadow-xl">
              <div class="flex px-4 pt-5 pb-2">
                <button type="button" class="-m-2 inline-flex items-center justify-center rounded-md p-2 text-gray-400" @click="mobileMenuOpen = false">
                  <span class="sr-only">Close menu</span>
                  <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                </button>
              </div>

              <!-- Links -->
              <TabGroup as="div" class="mt-2">
                <div class="border-b border-gray-200">
                  <TabList class="-mb-px flex space-x-8 px-4">
                    <Tab v-for="category in navigation.categories" :key="category.name" v-slot="{ selected }" as="template">
                      <button class="flex-1 whitespace-nowrap border-b-2 py-4 px-1 text-base font-medium" :class="[selected ? 'text-brand-primary border-brand-primary' : 'text-gray-900 border-transparent']">
                        {{ category.name }}
                      </button>
                    </Tab>
                  </TabList>
                </div>
                <TabPanels as="template">
                  <TabPanel v-for="(category, categoryIdx) in navigation.categories" :key="category.name" class="space-y-12 px-4 pt-10 pb-6">
                    <div class="grid grid-cols-1 items-start gap-y-10 gap-x-6">
                      <div class="grid grid-cols-1 gap-y-10 gap-x-6">
                        <div>
                          <p :id="`mobile-featured-heading-${categoryIdx}`" class="font-medium text-gray-900">
                            Printers
                          </p>
                          <ul role="list" :aria-labelledby="`mobile-featured-heading-${categoryIdx}`" class="mt-6 space-y-6">
                            <li v-for="item in category.featured" :key="item.name" class="flex">
                              <a :href="item.href" class="text-gray-500">{{ item.name }}</a>
                            </li>
                          </ul>
                        </div>
                        <div>
                          <p id="mobile-categories-heading" class="font-medium text-gray-900">
                            Solutions
                          </p>
                          <ul role="list" aria-labelledby="mobile-categories-heading" class="mt-6 space-y-6">
                            <li v-for="item in category.categories" :key="item.name" class="flex">
                              <a :href="item.href" class="text-gray-500">{{ item.name }}</a>
                            </li>
                          </ul>
                        </div>
                      </div>
                    </div>
                  </TabPanel>
                </TabPanels>
              </TabGroup>

              <div class="space-y-6 border-t border-gray-200 py-6 px-4">
                <div class="flow-root">
                  <a href="#" class="-m-2 block p-2 font-medium text-gray-900">Create an account</a>
                </div>
                <div class="flow-root">
                  <a href="#" class="-m-2 block p-2 font-medium text-gray-900">Sign in</a>
                </div>
              </div>
            </DialogPanel>
          </TransitionChild>
        </div>
      </Dialog>
    </TransitionRoot>

    <header class="relative z-10">
      <nav aria-label="Top">
        <!-- Secondary navigation -->
        <div class="bg-white">
          <div class="border-b border-gray-200">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
              <div class="flex h-16 items-center justify-between">
                <!-- Logo (lg+) -->
                <div class="hidden lg:flex lg:items-center">
                  <a href="/">
                    <span class="sr-only">Bixolon</span>
                    <img class="h-5 w-auto" src="/bixolon_orange_logo.jpeg" alt="">
                  </a>
                </div>

                <div class="hidden h-full lg:flex">
                  <!-- Mega menus -->
                  <PopoverGroup class="hidden lg:block lg:flex-1 lg:self-stretch">
                    <div class="flex h-full space-x-8">
                      <Popover v-for="category in navigation.categories" :key="category.name" v-slot="{ open }" class="flex">
                        <div class="relative flex">
                          <PopoverButton class="relative z-10 flex items-center justify-center text-sm font-medium transition-colors duration-200 ease-out outline-none" :class="[open ? 'text-brand-primary' : 'text-gray-700 hover:text-gray-800']">
                            {{ category.name }}
                            <span class="absolute inset-x-0 bottom-0 h-0.5 transition-colors duration-200 ease-out sm:mt-5 sm:translate-y-px sm:transform" :class="[open ? 'bg-brand-primary' : '']" aria-hidden="true" />
                          </PopoverButton>
                        </div>

                        <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0" enter-to-class="opacity-100" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100" leave-to-class="opacity-0">
                          <PopoverPanel class="absolute inset-x-0 top-full">
                            <!-- Presentational element used to render the bottom shadow, if we put the shadow on the actual panel it pokes out the top, so we use this shorter element to hide the top of the shadow -->
                            <div class="absolute inset-0 top-1/2 bg-white shadow" aria-hidden="true" />

                            <div class="relative bg-white">
                              <div class="mx-auto max-w-7xl px-8">
                                <div class="grid grid-cols-2 gap-y-10 gap-x-32 py-16">
                                  <div class="grid grid-cols-2 grid-rows-1 gap-8 text-sm">
                                    <div v-for="(item, itemIdx) in category.featured" :key="item.name" class="group aspect-w-1 aspect-h-1 relative overflow-hidden rounded-md bg-gray-100" :class="[itemIdx === 0 ? 'aspect-w-2 col-span-2' : '']">
                                      <img :src="item.imageSrc" :alt="item.imageAlt" class="object-cover object-center group-hover:opacity-75">
                                      <div class="flex flex-col justify-end">
                                        <div class="bg-white bg-opacity-60 p-4 text-sm">
                                          <a :href="item.href" class="font-medium text-gray-900">
                                            <span class="absolute inset-0" aria-hidden="true" />
                                            {{ item.name }}
                                          </a>
                                          <p aria-hidden="true" class="mt-0.5 text-gray-700 sm:mt-1">
                                            Explore now
                                          </p>
                                        </div>
                                      </div>
                                    </div>
                                  </div>
                                  <div class="grid grid-cols-3 gap-y-10 gap-x-8 text-sm text-gray-500">
                                    <div v-for="(column, columnIdx) in category.sections" :key="columnIdx" class="space-y-10">
                                      <div v-for="section in column" :key="section.name">
                                        <p :id="`${category.id}-${section.id}-heading`" class="font-medium text-gray-900">
                                          {{ section.xxx }}
                                        </p>
                                        <ul role="list" :aria-labelledby="`${category.id}-${section.id}-heading`" class="mt-4 space-y-4">
                                          <li v-for="item in section.items" :key="item.name" class="flex">
                                            <a :href="item.href" class="hover:text-gray-800">{{ item.name }}</a>
                                          </li>
                                        </ul>
                                      </div>
                                    </div>
                                  </div>
                                </div>
                              </div>
                            </div>
                          </PopoverPanel>
                        </transition>
                      </Popover>
                      <div class="space-x-8 relative z-10 flex items-center justify-center text-sm font-medium transition-colors duration-200 ease-out outline-none">
                        <div v-for="page in navigation.pages" :key="page.name" class="flow-root">
                          <a :href="page.href" class="-m-2 block p-2 font-medium text-gray-900">{{ page.name }}</a>
                        </div>
                        <div>
                          <Disclosure v-slot="{ open }" as="nav" class="bg-white">
                            <div class="mx-auto max-w-7xl px-2 sm:px-4 lg:px-8">
                              <div class="flex h-16 justify-between">
                                <div class="flex flex-1 items-center justify-center px-2 lg:ml-6 lg:justify-end">
                                  <div class="w-full max-w-lg lg:max-w-xs">
                                    <label for="search" class="sr-only">Search</label>
                                    <div class="relative">
                                      <div class="pointer-events-none absolute inset-y-0 left-0 flex items-center pl-3">
                                        <MagnifyingGlassIcon class="h-5 w-5 text-gray-400" aria-hidden="true" />
                                      </div>
                                      <input id="search" name="search" class="pr-8 text-gray-700 block w-full rounded-md bg-white py-2 pl-10 pr-3 leading-5 placeholder-gray-500 focus:placeholder-gray-400 focus:outline-none focus:ring-1 sm:text-sm" placeholder="Type to search..." type="search">
                                      <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center pr-3 text-gray-400">
                                        <svg id="icon" class="w-4 h-4" fill="currentColor" viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg">
                                          <path d="M24,13a4,4,0,0,0,4-4V8a4,4,0,0,0-4-4H23a4,4,0,0,0-4,4v3H13V8A4,4,0,0,0,9,4H8A4,4,0,0,0,4,8V9a4,4,0,0,0,4,4h3v6H8a4,4,0,0,0-4,4v1a4,4,0,0,0,4,4H9a4,4,0,0,0,4-4V21h6v3a4,4,0,0,0,4,4h1a4,4,0,0,0,4-4V23a4,4,0,0,0-4-4H21V13ZM21,8a2,2,0,0,1,2-2h1a2,2,0,0,1,2,2V9a2,2,0,0,1-2,2H21ZM8,11A2,2,0,0,1,6,9V8A2,2,0,0,1,8,6H9a2,2,0,0,1,2,2v3H8Zm3,13a2,2,0,0,1-2,2H8a2,2,0,0,1-2-2V23a2,2,0,0,1,2-2h3Zm8-5H13V13h6Zm2,2h3a2,2,0,0,1,2,2v1a2,2,0,0,1-2,2H23a2,2,0,0,1-2-2Z" />
                                          <rect id="_Transparent_Rectangle_" data-name="&lt;Transparent Rectangle&gt;" class="cls-1" width="32" height="32" />
                                        </svg>
                                        K
                                      </div>
                                    </div>
                                  </div>
                                  <div class="flex items-center lg:hidden">
                                    <!-- Mobile menu button -->
                                    <DisclosureButton class="inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-100 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-inset">
                                      <span class="sr-only">Open main menu</span>
                                      <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
                                      <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
                                    </DisclosureButton>
                                  </div>
                                  <div class="hidden lg:ml-4 lg:flex lg:items-center">
                                    <button type="button" class="flex-shrink-0 rounded-full bg-white p-1 text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-offset-2">
                                      <span class="sr-only">View notifications</span>
                                      <BellIcon class="h-6 w-6" aria-hidden="true" />
                                    </button>

                                    <!-- Profile dropdown -->
                                    <Menu as="div" class="relative ml-4 flex-shrink-0">
                                      <div>
                                        <MenuButton class="flex rounded-full bg-white text-sm focus:outline-none focus:ring-2 focus:ring-offset-2">
                                          <span class="sr-only">Open user menu</span>
                                          <img class="h-8 w-8 rounded-full" src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
                                        </MenuButton>
                                      </div>
                                      <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75" leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
                                        <MenuItems class="absolute right-0 z-10 mt-2 w-48 origin-top-right rounded-md bg-white py-1 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                                          <MenuItem v-slot="{ active }">
                                            <a href="#" class="block px-4 py-2 text-sm text-gray-700" :class="[active ? 'bg-gray-100' : '']">Your Profile</a>
                                          </MenuItem>
                                          <MenuItem v-slot="{ active }">
                                            <a href="#" class="block px-4 py-2 text-sm text-gray-700" :class="[active ? 'bg-gray-100' : '']">Settings</a>
                                          </MenuItem>
                                          <MenuItem v-slot="{ active }">
                                            <a href="/login" class="block px-4 py-2 text-sm text-gray-700" :class="[active ? 'bg-gray-100' : '']">Sign out</a>
                                          </MenuItem>
                                        </MenuItems>
                                      </transition>
                                    </Menu>
                                  </div>
                                </div>
                              </div>

                              <DisclosurePanel class="lg:hidden">
                                <div class="border-t border-gray-200 pt-4 pb-3">
                                  <div class="flex items-center px-4">
                                    <div class="flex-shrink-0">
                                      <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
                                    </div>
                                    <div class="ml-3">
                                      <div class="text-base font-medium text-gray-800">
                                        Liz Crouch
                                      </div>
                                      <div class="text-sm font-medium text-gray-500">
                                        liz@example.com
                                      </div>
                                    </div>
                                    <button type="button" class="ml-auto flex-shrink-0 rounded-full bg-white p-1 text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-orange-500 focus:ring-offset-2">
                                      <span class="sr-only">View notifications</span>
                                      <BellIcon class="h-6 w-6" aria-hidden="true" />
                                    </button>
                                  </div>
                                  <div class="mt-3 space-y-1">
                                    <DisclosureButton as="a" href="#" class="block px-4 py-2 text-base font-medium text-gray-500 hover:bg-gray-100 hover:text-gray-800">
                                      Your Profile
                                    </DisclosureButton>
                                    <DisclosureButton as="a" href="#" class="block px-4 py-2 text-base font-medium text-gray-500 hover:bg-gray-100 hover:text-gray-800">
                                      Settings
                                    </DisclosureButton>
                                    <DisclosureButton as="a" href="#" class="block px-4 py-2 text-base font-medium text-gray-500 hover:bg-gray-100 hover:text-gray-800">
                                      Sign out
                                    </DisclosureButton>
                                  </div>
                                </div>
                              </DisclosurePanel>
                            </div>
                          </Disclosure>
                        </div>
                      </div>
                    </div>

                    <!-- Mobile menu and search (lg-) -->
                    <div class="flex flex-1 items-center lg:hidden">
                      <button type="button" class="-ml-2 rounded-md bg-white p-2 text-gray-400" @click="mobileMenuOpen = true">
                        <span class="sr-only">Open menu</span>
                        <Bars3Icon class="h-6 w-6" aria-hidden="true" />
                      </button>
                    </div>

                    <!-- Logo (lg-) -->
                    <a href="/" class="lg:hidden">
                      <span class="sr-only">Bixolon</span>
                      <img src="/bixolon_orange_logo.jpeg" alt="" class="h-4 w-auto">
                    </a>
                  </PopoverGroup>
                </div>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </header>
  </div>
</template>

<style scoped>
.cls-1 {
  fill: none;
}
</style>
