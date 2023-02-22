<script setup>
import { ref } from 'vue'
import {
  Dialog,
  DialogPanel,
  Popover,
  PopoverButton,
  PopoverGroup,
  PopoverPanel,
  Tab,
  TabGroup,
  TabList,
  TabPanel,
  TabPanels,
  TransitionChild,
  TransitionRoot,
} from '@headlessui/vue'
import { Bars3Icon, MagnifyingGlassIcon, ShoppingCartIcon, UserIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import { ChevronDownIcon } from '@heroicons/vue/20/solid'

const currencies = ['CAD', 'USD', 'AUD', 'EUR', 'GBP']
const navigation = {
  categories: [
    {
      name: 'Products',
      featured: [
        { name: 'POS Printers', href: '#' },
        { name: 'Label Printers', href: '#' },
        { name: 'Linerless Printers', href: '#' },
        { name: 'SOHO Printers', href: '#' },
        { name: 'Mobile Printers', href: '#' },
        { name: 'Kiosk Printers', href: '#' },
        { name: 'POS Peripherals', href: '#' },
        { name: 'Accessories', href: '#' },
      ],
      categories: [
        { name: 'Full Nelson', href: '#' },
        { name: 'My Way', href: '#' },
        { name: 'Re-Arranged', href: '#' },
        { name: 'Counterfeit', href: '#' },
        { name: 'Significant Other', href: '#' },
      ],
    },
    {
      name: 'Solutions',
      featured: [
        { name: 'Retail', href: '#' },
        { name: 'Hospitality', href: '#' },
        { name: 'Manufacturing', href: '#' },
        { name: 'Transportation', href: '#' },
        { name: 'Healthcare', href: '#' },
        { name: 'Public Sector', href: '#' },
        { name: 'Ticketing', href: '#' },
        { name: 'Aviation', href: '#' },
      ],
      collection: [
        { name: 'Everything', href: '#' },
        { name: 'Core', href: '#' },
        { name: 'New Arrivals', href: '#' },
        { name: 'Sale', href: '#' },
      ],
      categories: [
        { name: 'Artwork Tees', href: '#' },
        { name: 'Pants', href: '#' },
        { name: 'Accessories', href: '#' },
        { name: 'Boxers', href: '#' },
        { name: 'Basic Tees', href: '#' },
      ],
      brands: [
        { name: 'Significant Other', href: '#' },
        { name: 'My Way', href: '#' },
        { name: 'Counterfeit', href: '#' },
        { name: 'Re-Arranged', href: '#' },
        { name: 'Full Nelson', href: '#' },
      ],
    },
  ],
  pages: [
    { name: 'Support', href: '#' },
    { name: 'Unite Partner Program', href: '#' },
    { name: 'About', href: '#' },
  ],
}
const collections = [
  {
    id: 1,
    name: 'SRP-S3000',
    description_1: '3-inch Linerless Printer',
    description_2: 'Feature-Rich',
    description_3: 'Premium',
    href: '/products/1',
    imageSrc: '../../../public/printer_1.jpeg',
    price: '$35',
  },
  {
    id: 2,
    name: 'SRP-S300',
    description_1: '3 inch Re-Stick',
    description_2: 'Label and Receipt',
    description_3: 'Direct Thermal Printer',
    href: '/products/2',
    imageSrc: '../../../public/printer_2.jpeg',
    price: '$35',
  },
  {
    id: 3,
    name: 'SRP-S200',
    description_1: '2-inch Direct Thermal',
    description_2: 'Linerless Printer',
    description_3: 'Compact and Economical',
    href: '/products/3',
    imageSrc: '../../../public/printer_3.jpeg',
    price: '$35',
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
const footerNavigation = {
  products: [
    { name: 'POS Printers', href: '#' },
    { name: 'Label Printers', href: '#' },
    { name: 'Linerless Printers', href: '#' },
    { name: 'SOHO Printers', href: '#' },
    { name: 'Mobile Printers', href: '#' },
    { name: 'Kiosk Printers', href: '#' },
    { name: 'POS Peripherals', href: '#' },
    { name: 'Accessories', href: '#' },
  ],
  support: [
    { name: 'Technical Support', href: '#' },
    { name: 'Shipping', href: '#' },
    { name: 'Returns', href: '#' },
    { name: 'Warranty', href: '#' },
    { name: 'Secure Payments', href: '#' },
    { name: 'FAQ', href: '#' },
    { name: 'Find a store', href: '#' },
  ],
  company: [
    { name: 'Who we are', href: '#' },
    { name: 'Sustainability', href: '#' },
    { name: 'Press', href: '#' },
    { name: 'Careers', href: '#' },
    { name: 'Terms & Conditions', href: '#' },
    { name: 'Privacy', href: '#' },
  ],
  legal: [
    { name: 'Terms of Service', href: '#' },
    { name: 'Return Policy', href: '#' },
    { name: 'Privacy Policy', href: '#' },
    { name: 'Shipping Policy', href: '#' },
  ],
  bottomLinks: [
    { name: 'Accessibility', href: '#' },
    { name: 'Privacy', href: '#' },
    { name: 'Terms', href: '#' },
  ],
}

const mobileMenuOpen = ref(false)
</script>

<template>
  <div class="bg-white">
    <main>
      <!-- Hero -->
      <div class="flex flex-col border-b border-gray-200 lg:border-0">
        <div class="relative">
          <div aria-hidden="true" class="absolute hidden h-full w-1/2 bg-gray-100 lg:block" />
          <div class="relative bg-white">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:grid lg:grid-cols-2 lg:px-8">
              <div class="mx-auto max-w-2xl py-24 lg:max-w-none lg:py-64">
                <div class="lg:pr-16">
                  <h1 class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl xl:text-6xl">
                    Focus on what matters
                  </h1>
                  <p class="mt-4 text-xl text-gray-600">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit
                  </p>
                  <div class="mt-6">
                    <a href="/products" class="inline-block rounded-md border border-transparent bg-brand-primary py-3 px-8 font-medium text-white hover:opacity-50">Shop Printers</a>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="h-48 w-full sm:h-64 lg:absolute lg:top-0 lg:right-0 lg:h-full lg:w-1/2">
            <img src="../../../public/bixolon-content.jpg" alt="" class="h-full w-full object-cover object-center">
          </div>
        </div>
      </div>

      <!-- Collections -->
      <section aria-labelledby="collections-heading" class="bg-gray-100">
        <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
          <div class="mx-auto max-w-2xl py-16 sm:py-24 lg:max-w-none lg:py-32">
            <h2 id="collections-heading" class="text-2xl font-bold text-gray-900">
              Products
            </h2>

            <div class="mt-6 space-y-12 lg:grid lg:grid-cols-3 lg:gap-x-6 lg:space-y-0">
              <div v-for="collection in collections" :key="collection.name" class="group relative">
                <div class="relative h-80 w-full overflow-hidden rounded-lg bg-white group-hover:opacity-75 sm:aspect-w-2 sm:aspect-h-1 sm:h-64 lg:aspect-w-1 lg:aspect-h-1">
                  <img :src="collection.imageSrc" :alt="collection.imageAlt" class="h-full w-full object-cover object-center">
                </div>
                <h3 class="mt-6 text-sm text-gray-500">
                  <a :href="collection.href">
                    <span class="absolute inset-0" />
                    {{ collection.name }}
                  </a>
                </h3>
                <p class="text-base font-semibold text-gray-900">
                  {{ collection.description_1 }}
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Sale and testimonials -->
      <div class="relative overflow-hidden">
        <!-- Decorative background image and gradient -->
        <div aria-hidden="true" class="absolute inset-0">
          <div class="absolute inset-0 mx-auto max-w-7xl overflow-hidden xl:px-8">
            <img src="https://tailwindui.com/img/ecommerce-images/home-page-02-sale-full-width.jpg" alt="" class="h-full w-full object-cover object-center">
          </div>
          <div class="absolute inset-0 bg-white bg-opacity-75" />
          <div class="absolute inset-0 bg-gradient-to-t from-white via-white" />
        </div>

        <!-- Sale -->
        <section aria-labelledby="sale-heading" class="relative mx-auto flex max-w-7xl flex-col items-center px-4 pt-32 text-center sm:px-6 lg:px-8">
          <div class="mx-auto max-w-2xl lg:max-w-none">
            <h2 id="sale-heading" class="text-4xl font-bold tracking-tight text-gray-900 sm:text-5xl lg:text-6xl">
              Get 25% off during our one-time sale
            </h2>
            <p class="mx-auto mt-4 max-w-xl text-xl text-gray-600">
              Most of our products are limited releases that won't come back. Get your favorite items while they're in stock.
            </p>
            <a href="#" class="mt-6 inline-block w-full rounded-md border border-transparent bg-brand-primary py-3 px-8 font-medium text-white hover:opacity-50 sm:w-auto">Get access to our one-time sale</a>
          </div>
        </section>

        <!-- Testimonials -->
        <section aria-labelledby="testimonial-heading" class="relative mx-auto max-w-7xl py-24 px-4 sm:px-6 lg:py-32 lg:px-8">
          <div class="mx-auto max-w-2xl lg:max-w-none">
            <h2 id="testimonial-heading" class="text-2xl font-bold tracking-tight text-gray-900">
              What are people saying?
            </h2>

            <div class="mt-16 space-y-16 lg:grid lg:grid-cols-3 lg:gap-x-8 lg:space-y-0">
              <blockquote v-for="testimonial in testimonials" :key="testimonial.id" class="sm:flex lg:block">
                <svg width="24" height="18" viewBox="0 0 24 18" aria-hidden="true" class="flex-shrink-0 text-gray-300">
                  <path d="M0 18h8.7v-5.555c-.024-3.906 1.113-6.841 2.892-9.68L6.452 0C3.188 2.644-.026 7.86 0 12.469V18zm12.408 0h8.7v-5.555C21.083 8.539 22.22 5.604 24 2.765L18.859 0c-3.263 2.644-6.476 7.86-6.451 12.469V18z" fill="currentColor" />
                </svg>
                <div class="mt-8 sm:mt-0 sm:ml-6 lg:mt-10 lg:ml-0">
                  <p class="text-lg text-gray-600">
                    {{ testimonial.quote }}
                  </p>
                  <cite class="mt-4 block font-semibold not-italic text-gray-900">{{ testimonial.attribution }}</cite>
                </div>
              </blockquote>
            </div>
          </div>
        </section>
      </div>
    </main>
  </div>
</template>
