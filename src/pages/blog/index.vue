<script setup>
import { ref } from 'vue'
import {
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
  TransitionChild,
  TransitionRoot,
} from '@headlessui/vue'
import { XMarkIcon } from '@heroicons/vue/24/outline'
import { ChevronDownIcon, ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/20/solid'
const sortOptions = [
  { name: 'Most Popular', href: '#' },
  { name: 'Best Rating', href: '#' },
  { name: 'Newest', href: '#' },
]
const filters = [
  {
    id: 'category',
    name: 'Products',
    options: [
      { value: 'tees', label: 'Label Printing' },
      { value: 'crewnecks', label: 'Linerless Printing' },
      { value: 'hats', label: 'Mobile Printing' },
      { value: 'hats', label: 'mPOS' },
      { value: 'hats', label: 'Mobile POS' },
      { value: 'hats', label: 'RFID Printing' },
      { value: 'hats', label: 'Software' },
      { value: 'hats', label: 'Supplies' },
    ],
  },
  {
    id: 'brand',
    name: 'Solution',
    options: [
      { value: 'clothing-company', label: 'E-Commerce' },
      { value: 'fashion-inc', label: 'Government' },
      { value: 'shoes-n-more', label: 'Healthcare' },
      { value: 'shoes-n-more', label: 'Hospitality' },
      { value: 'shoes-n-more', label: 'Manufacturing' },
      { value: 'shoes-n-more', label: 'Payment' },
      { value: 'shoes-n-more', label: 'Retail' },
      { value: 'shoes-n-more', label: 'Transportation & Logistics' },
    ],
  },
  {
    id: 'color',
    name: 'Subject',
    options: [
      { value: 'white', label: 'Corporate' },
      { value: 'black', label: 'Event' },
      { value: 'grey', label: 'Partnership' },
      { value: 'grey', label: 'Product Launch' },
    ],
  },
  {
    id: 'sizes',
    name: 'Sizes',
    options: [
      { value: 's', label: 'S' },
      { value: 'm', label: 'M' },
      { value: 'l', label: 'L' },
    ],
  },
]

const open = ref(false)

const posts = [
  {
    id: 1,
    title: 'BIXOLON Announces New HQ Office in South Korea',
    href: '/blog',
    description:
      'BIXOLON Co., Ltd., a leading global Mobile, Label and POS Printer manufacturer, today announced the relocation of its HQ office effective February 20, 2023. The move supports the company’s multi-year strategic growth plan and is located in a prominent area of Pangyo Techno Valley, South Korea.',
    imageUrl:
      '/blog_hq.jpeg',
    date: 'Feb 20, 2023',
    datetime: '2020-03-16',
    category: { title: 'Corporate', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
  {
    id: 2,
    title: 'BIXOLON Demonstrates its Complete Range of Retail Printing Solutions at EuroShop 2023',
    href: '/blog',
    description: 'EuroShop – (26.02.2023 – 02.03.2023, Dusseldorf, Germany) BIXOLON, the global manufacturer of advanced Receipt, Label and Mobile printers welcomes visitors onto stand #6A32 throughout the show, where it will be showcasing its sophisticated range of Retail printing solutions to the European market.',
    imageUrl: '/blog_2.jpeg',
    date: 'Feb 7, 2023',
    datetime: '2020-03-16',
    category: { title: 'Event', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
  {
    id: 3,
    title: 'How to Efficiently Print Shipping Labels for e-commerce Businesses',
    href: '/blog',
    description: 'Printing online shipping labels has a significant role in the success of an e-commerce business. With several printing options to choose from, we understand it can be hard to know which is right for your business.',
    imageUrl: '/blog_3.jpeg',
    date: 'Jan 31, 2023',
    datetime: '2020-03-16',
    category: { title: 'Tech & Trend', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
  {
    id: 4,
    title: 'BIXOLON Announces New HQ Office in South Korea',
    href: '/blog',
    description:
      'BIXOLON Co., Ltd., a leading global Mobile, Label and POS Printer manufacturer, today announced the relocation of its HQ office effective February 20, 2023. The move supports the company’s multi-year strategic growth plan and is located in a prominent area of Pangyo Techno Valley, South Korea.',
    imageUrl:
      '/blog_hq.jpeg',
    date: 'Feb 20, 2023',
    datetime: '2020-03-16',
    category: { title: 'Corporate', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
  {
    id: 5,
    title: 'BIXOLON Demonstrates its Complete Range of Retail Printing Solutions at EuroShop 2023',
    href: '/blog',
    description: 'EuroShop – (26.02.2023 – 02.03.2023, Dusseldorf, Germany) BIXOLON, the global manufacturer of advanced Receipt, Label and Mobile printers welcomes visitors onto stand #6A32 throughout the show, where it will be showcasing its sophisticated range of Retail printing solutions to the European market.',
    imageUrl: '/blog_2.jpeg',
    date: 'Feb 7, 2023',
    datetime: '2020-03-16',
    category: { title: 'Event', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
  {
    id: 6,
    title: 'How to Efficiently Print Shipping Labels for e-commerce Businesses',
    href: '/blog',
    description: 'Printing online shipping labels has a significant role in the success of an e-commerce business. With several printing options to choose from, we understand it can be hard to know which is right for your business.',
    imageUrl: '/blog_3.jpeg',
    date: 'Jan 31, 2023',
    datetime: '2020-03-16',
    category: { title: 'Tech & Trend', href: '/blog' },
    author: {
      name: 'Liz Crouch',
      role: 'Marketing Manager',
      href: '/blog',
      imageUrl:
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80',
    },
  },
]
</script>

<template>
  <div class="bg-white py-24 sm:py-32 border-t border-gray-200">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <!-- Mobile filter dialog -->
      <TransitionRoot as="template" :show="open">
        <Dialog as="div" class="relative z-40 sm:hidden" @close="open = false">
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
                  <button type="button" class="-mr-2 flex h-10 w-10 items-center justify-center rounded-md bg-white p-2 text-gray-400 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-orange-500" @click="open = false">
                    <span class="sr-only">Close menu</span>
                    <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                  </button>
                </div>

                <!-- Filters -->
                <form class="mt-4">
                  <Disclosure v-for="section in filters" :key="section.name" v-slot="{ open }" as="div" class="border-t border-gray-200 px-4 py-6">
                    <h3 class="-mx-2 -my-3 flow-root">
                      <DisclosureButton class="flex w-full items-center justify-between bg-white px-2 py-3 text-sm text-gray-400">
                        <span class="font-medium text-gray-900">{{ section.name }}</span>
                        <span class="ml-6 flex items-center">
                          <ChevronDownIcon class="h-5 w-5 transform" :class="[open ? '-rotate-180' : 'rotate-0']" aria-hidden="true" />
                        </span>
                      </DisclosureButton>
                    </h3>
                    <DisclosurePanel class="pt-6">
                      <div class="space-y-6">
                        <div v-for="(option, optionIdx) in section.options" :key="option.value" class="flex items-center">
                          <input :id="`filter-mobile-${section.id}-${optionIdx}`" :name="`${section.id}[]`" :value="option.value" type="checkbox" class="h-4 w-4 rounded border-gray-300 text-orange-600 focus:ring-orange-500">
                          <label :for="`filter-mobile-${section.id}-${optionIdx}`" class="ml-3 text-sm text-gray-500">{{ option.label }}</label>
                        </div>
                      </div>
                    </DisclosurePanel>
                  </Disclosure>
                </form>
              </DialogPanel>
            </TransitionChild>
          </div>
        </Dialog>
      </TransitionRoot>

      <div class="mx-auto max-w-3xl px-4 text-center sm:px-6 lg:max-w-7xl lg:px-8">
        <div class="pb-24">
          <h1 class="text-4xl font-bold tracking-tight text-gray-900">
            From the blog
          </h1>
          <p class="mx-auto mt-4 max-w-3xl text-base text-gray-500">
            The printing industry’s latest technologies & trends.
          </p>
        </div>

        <section aria-labelledby="filter-heading" class="border-t border-gray-200 py-6">
          <h2 id="filter-heading" class="sr-only">
            Product filters
          </h2>

          <div class="flex items-center justify-between">
            <Menu as="div" class="relative inline-block text-left">
              <div>
                <MenuButton class="group inline-flex justify-center text-sm font-medium text-gray-700 hover:text-gray-900">
                  Sort
                  <ChevronDownIcon class="-mr-1 ml-1 h-5 w-5 flex-shrink-0 text-gray-400 group-hover:text-gray-500" aria-hidden="true" />
                </MenuButton>
              </div>

              <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75" leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
                <MenuItems class="absolute left-0 z-10 mt-2 w-40 origin-top-left rounded-md bg-white shadow-2xl ring-1 ring-black ring-opacity-5 focus:outline-none">
                  <div class="py-1">
                    <MenuItem v-for="option in sortOptions" :key="option" v-slot="{ active }">
                      <a :href="option.href" class="block px-4 py-2 text-sm font-medium text-gray-900" :class="[active ? 'bg-gray-100' : '']">{{ option.name }}</a>
                    </MenuItem>
                  </div>
                </MenuItems>
              </transition>
            </Menu>

            <button type="button" class="inline-block text-sm font-medium text-gray-700 hover:text-gray-900 sm:hidden" @click="open = true">
              Filters
            </button>

            <PopoverGroup class="hidden sm:flex sm:items-baseline sm:space-x-8">
              <Popover v-for="(section, sectionIdx) in filters" :id="`desktop-menu-${sectionIdx}`" :key="section.name" as="div" class="relative inline-block text-left">
                <div>
                  <PopoverButton class="group inline-flex items-center justify-center text-sm font-medium text-gray-700 hover:text-gray-900">
                    <span>{{ section.name }}</span>
                    <span v-if="sectionIdx === 0" class="ml-1.5 rounded bg-gray-200 py-0.5 px-1.5 text-xs font-semibold tabular-nums text-gray-700">1</span>
                    <ChevronDownIcon class="-mr-1 ml-1 h-5 w-5 flex-shrink-0 text-gray-400 group-hover:text-gray-500" aria-hidden="true" />
                  </PopoverButton>
                </div>

                <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95" enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75" leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
                  <PopoverPanel class="absolute right-0 z-10 mt-2 origin-top-right rounded-md bg-white p-4 shadow-2xl ring-1 ring-black ring-opacity-5 focus:outline-none">
                    <form class="space-y-4">
                      <div v-for="(option, optionIdx) in section.options" :key="option.value" class="flex items-center">
                        <input :id="`filter-${section.id}-${optionIdx}`" :name="`${section.id}[]`" :value="option.value" type="checkbox" class="h-4 w-4 rounded border-gray-300 text-orange-600 focus:ring-orange-500">
                        <label :for="`filter-${section.id}-${optionIdx}`" class="ml-3 whitespace-nowrap pr-6 text-sm font-medium text-gray-900">{{ option.label }}</label>
                      </div>
                    </form>
                  </PopoverPanel>
                </transition>
              </Popover>
            </PopoverGroup>
          </div>
        </section>
      </div>

      <div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-y-20 gap-x-8 lg:mx-0 lg:max-w-none lg:grid-cols-3">
        <article v-for="post in posts" :key="post.id" class="flex flex-col items-start justify-between">
          <div class="relative w-full">
            <a :href="post.href">
              <img :src="post.imageUrl" alt="" class="w-full rounded-2xl bg-gray-100 object-cover min-h-50">
              <div class="absolute inset-0 rounded-2xl ring-1 ring-inset ring-gray-900/10" />
            </a>
          </div>
          <div class="max-w-xl">
            <div class="mt-8 flex items-center gap-x-4 text-xs">
              <time :datetime="post.datetime" class="text-gray-500">{{ post.date }}</time>
              <a :href="post.category.href" class="relative z-10 rounded-full bg-gray-50 py-1.5 px-3 font-medium text-gray-600 hover:bg-gray-100">{{ post.category.title }}</a>
            </div>
            <div class="group relative">
              <h3 class="mt-3 text-lg font-semibold leading-6 text-gray-900 group-hover:text-gray-600">
                <a :href="post.href">
                  <span class="absolute inset-0" />
                  {{ post.title }}
                </a>
              </h3>
              <p class="mt-5 text-sm leading-6 text-gray-600 line-clamp-3">
                {{ post.description }}
              </p>
            </div>
            <div class="relative mt-8 flex items-center gap-x-4">
              <img :src="post.author.imageUrl" alt="" class="h-10 w-10 rounded-full bg-gray-100">
              <div class="text-sm leading-6">
                <p class="font-semibold text-gray-900">
                  <a :href="post.author.href">
                    <span class="absolute inset-0" />
                    {{ post.author.name }}
                  </a>
                </p>
                <p class="text-gray-600">
                  {{ post.author.role }}
                </p>
              </div>
            </div>
          </div>
        </article>
      </div>

      <div class="flex items-center justify-between border-t border-gray-200 bg-white px-4 py-3 sm:px-6 mt-24">
        <div class="flex flex-1 justify-between sm:hidden">
          <a href="#" class="relative inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 hover:bg-gray-50">Previous</a>
          <a href="#" class="relative ml-3 inline-flex items-center rounded-md border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700 hover:bg-gray-50">Next</a>
        </div>
        <div class="hidden sm:flex sm:flex-1 sm:items-center sm:justify-between">
          <div>
            <p class="text-sm text-gray-700">
              Showing
              {{ ' ' }}
              <span class="font-medium">1</span>
              {{ ' ' }}
              to
              {{ ' ' }}
              <span class="font-medium">10</span>
              {{ ' ' }}
              of
              {{ ' ' }}
              <span class="font-medium">97</span>
              {{ ' ' }}
              results
            </p>
          </div>
          <div>
            <nav class="isolate inline-flex -space-x-px rounded-md shadow-sm" aria-label="Pagination">
              <a href="#" class="relative inline-flex items-center rounded-l-md border border-gray-300 bg-white px-2 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20">
                <span class="sr-only">Previous</span>
                <ChevronLeftIcon class="h-5 w-5" aria-hidden="true" />
              </a>
              <!-- Current: "z-10 bg-orange-50 border-orange-500 text-orange-600", Default: "bg-white border-gray-300 text-gray-500 hover:bg-gray-50" -->
              <a href="#" aria-current="page" class="relative z-10 inline-flex items-center border border-orange-500 bg-orange-50 px-4 py-2 text-sm font-medium text-orange-600 focus:z-20">1</a>
              <a href="#" class="relative inline-flex items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20">2</a>
              <a href="#" class="relative hidden items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20 md:inline-flex">3</a>
              <span class="relative inline-flex items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-700">...</span>
              <a href="#" class="relative hidden items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20 md:inline-flex">8</a>
              <a href="#" class="relative inline-flex items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20">9</a>
              <a href="#" class="relative inline-flex items-center border border-gray-300 bg-white px-4 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20">10</a>
              <a href="#" class="relative inline-flex items-center rounded-r-md border border-gray-300 bg-white px-2 py-2 text-sm font-medium text-gray-500 hover:bg-gray-50 focus:z-20">
                <span class="sr-only">Next</span>
                <ChevronRightIcon class="h-5 w-5" aria-hidden="true" />
              </a>
            </nav>
          </div>
        </div>
      </div>
    </div>

    <div class="pt-24">
      <!-- <div class="mx-auto max-w-7xl sm:px-6 lg:px-8">
        <div class="relative isolate flex flex-col gap-10 overflow-hidden bg-gray-900 px-6 py-24 shadow-2xl sm:rounded-3xl sm:px-24 xl:flex-row xl:items-center xl:py-32">
          <h2 class="max-w-2xl text-3xl font-bold tracking-tight text-white sm:text-4xl xl:max-w-none xl:flex-auto">
            Get notified when we’re sharing news.
          </h2>
          <form class="w-full max-w-md">
            <div class="flex gap-x-4">
              <label for="email-address" class="sr-only">Email address</label>
              <input id="email-address" name="email" type="email" autocomplete="email" required="" class="min-w-0 flex-auto rounded-md border-0 bg-white/5 px-3.5 py-2 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-white sm:text-sm sm:leading-6" placeholder="Enter your email">
              <button type="submit" class="flex-none rounded-md bg-white py-2.5 px-3.5 text-sm font-semibold text-gray-900 shadow-sm hover:bg-gray-100 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-white">
                Notify me
              </button>
            </div>
            <p class="mt-4 text-sm leading-6 text-gray-300">
              We care about your data. Read our <a href="#" class="font-semibold text-white">privacy&nbsp;policy</a>.
            </p>
          </form>
          <svg viewBox="0 0 1024 1024" class="absolute top-1/2 left-1/2 -z-10 h-[64rem] w-[64rem] -translate-x-1/2" aria-hidden="true">
            <circle cx="512" cy="512" r="512" fill="url(#759c1415-0410-454c-8f7c-9a820de03641)" fill-opacity="0.7" />
            <defs>
              <radialGradient id="759c1415-0410-454c-8f7c-9a820de03641" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse" gradientTransform="translate(512 512) rotate(90) scale(512)">
                <stop stop-color="#e37b3b" />
                <stop offset="1" stop-color="#f59d78" stop-opacity="0" />
              </radialGradient>
            </defs>
          </svg>
        </div>
      </div> -->

      <div class="pt-24">
        <div class="mx-auto grid max-w-7xl grid-cols-1 gap-10 px-6 lg:grid-cols-12 lg:gap-8 lg:px-8">
          <div class="max-w-xl text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl lg:col-span-7">
            <h2 class="inline sm:block lg:inline xl:block">
              Want product news and updates?
            </h2>
            {{ ' ' }}
            <p class="inline sm:block lg:inline xl:block">
              Sign up for our newsletter.
            </p>
          </div>
          <form class="w-full max-w-md lg:col-span-5 lg:pt-2">
            <div class="flex gap-x-4">
              <label for="email-address" class="sr-only">Email address</label>
              <input id="email-address" name="email" type="email" autocomplete="email" required="" class="min-w-0 flex-auto rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-orange-600 sm:text-sm sm:leading-6" placeholder="Enter your email">
              <button type="submit" class="flex-none rounded-md bg-orange-600 py-2.5 px-3.5 text-sm font-semibold text-white shadow-sm hover:bg-orange-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-orange-600">
                Subscribe
              </button>
            </div>
            <p class="mt-4 text-sm leading-6 text-gray-900">
              We care about your data. Read our <a href="#" class="font-semibold text-orange-600 hover:text-orange-500">privacy&nbsp;policy</a>.
            </p>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
