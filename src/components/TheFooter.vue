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
    name: 'SRP-S300',
    description: 'Direct Thermal Printer',
    imageSrc: '../../../public/printer_1.jpeg',
    imageAlt: 'Desk with leather desk pad, walnut desk organizer, wireless keyboard and mouse, and porcelain mug.',
    href: '#',
  },
  {
    name: 'SRP-270',
    description: 'Receipt Printer',
    imageSrc: '../../../public/printer_2.jpeg',
    imageAlt: 'Wood table with porcelain mug, leather journal, brass pen, leather key ring, and a houseplant.',
    href: '#',
  },
  {
    name: 'STP-103III',
    description: 'POS Printer',
    imageSrc: '../../../public/printer_3.jpeg',
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
  <div>
    <footer aria-labelledby="footer-heading" class="bg-white">
      <h2 id="footer-heading" class="sr-only">
        Footer
      </h2>
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="border-t border-gray-200">
          <div class="pt-16 pb-20">
            <div class="md:flex md:justify-center">
              <img src="../../../public/bixolon_orange_logo.jpeg" alt="" class="h-5 w-auto">
            </div>
            <div class="mx-auto mt-16 max-w-5xl xl:grid xl:grid-cols-2 xl:gap-8">
              <div class="grid grid-cols-3 gap-8 xl:col-span-2">
                <div class="space-y-12 md:grid md:grid-cols-2 md:gap-8 md:space-y-0">
                  <div>
                    <h3 class="text-sm font-medium text-gray-900">
                      Products
                    </h3>
                    <ul role="list" class="mt-6 space-y-6">
                      <li v-for="item in footerNavigation.products" :key="item.name" class="text-sm">
                        <a :href="item.href" class="text-gray-500 hover:text-gray-600">{{ item.name }}</a>
                      </li>
                    </ul>
                  </div>
                  <div>
                    <h3 class="text-sm font-medium text-gray-900">
                      Customer Service
                    </h3>
                    <ul role="list" class="mt-6 space-y-6">
                      <li v-for="item in footerNavigation.support" :key="item.name" class="text-sm">
                        <a :href="item.href" class="text-gray-500 hover:text-gray-600">{{ item.name }}</a>
                      </li>
                    </ul>
                  </div>
                </div>
                <div class="space-y-12 md:grid md:grid-cols-2 md:gap-8 md:space-y-0">
                  <div>
                    <h3 class="text-sm font-medium text-gray-900">
                      Company
                    </h3>
                    <ul role="list" class="mt-6 space-y-6">
                      <li v-for="item in footerNavigation.company" :key="item.name" class="text-sm">
                        <a :href="item.href" class="text-gray-500 hover:text-gray-600">{{ item.name }}</a>
                      </li>
                    </ul>
                  </div>
                  <div>
                    <h3 class="text-sm font-medium text-gray-900">
                      Legal
                    </h3>
                    <ul role="list" class="mt-6 space-y-6">
                      <li v-for="item in footerNavigation.legal" :key="item.name" class="text-sm">
                        <a :href="item.href" class="text-gray-500 hover:text-gray-600">{{ item.name }}</a>
                      </li>
                    </ul>
                  </div>
                </div>
                <div class="space-y-12 md:grid md:grid-cols-1 md:gap-8 md:space-y-0 text-gray-900">
                  <div>
                    <div class="text-brand-primary font-bold text-lg">
                      BIXOLON America Inc.
                    </div>
                    <div class="mt-1 text-gray-500 text-sm">
                      <div class="mt-0.5">
                        2575 W 237th St, Torrance, CA 90505
                      </div>
                      <div class="mt-0.5">
                        Tel +1 858 764 4580
                      </div>
                      <div class="mt-0.5 text-xs text-gray-400">
                        <a href="bixolonusa.com">bixolonusa.com</a>
                      </div>
                    </div>
                  </div>
                  <div>
                    <div class="text-brand-primary font-bold text-lg">
                      BIXOLON Co., Ltd.
                    </div>
                    <div class="mt-1 text-gray-500 text-sm">
                      <div class="mt-0.5">
                        5F, IDIS Tower, 344 Pangyo-ro
                      </div>
                      <div class="mt-0.5">
                        Bundang-gu, Seongnam-si, Gyeonggi-do Republic of Korea, 13493
                      </div>
                      <div class="mt-0.5">
                        Tel +82 31 218 5500
                      </div>
                      <div class="mt-0.5 text-xs text-gray-400">
                        <a href="bixolon.com">bixolon.com</a>
                      </div>
                    </div>
                  </div>
                  <div>
                    <div class="text-brand-primary font-bold text-lg">
                      BIXOLON Europe GmbH
                    </div>
                    <div class="mt-1 text-gray-500 text-sm">
                      <div class="mt-0.5">
                        Tiefenbroicher Weg 35, 40472
                      </div>
                      <div class="mt-0.5">
                        Düsseldorf, Germany
                      </div>
                      <div class="mt-0.5">
                        Tel +49-211-68-78-54-0
                      </div>
                      <div class="mt-0.5 text-xs text-gray-400">
                        <a href="bixoloneu.com">bixoloneu.com</a>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="py-10 md:flex md:items-center md:justify-between">
          <div class="text-center md:text-left">
            <p class="text-sm text-gray-500">
              &copy; 2023 BIXOLON All Rights Reserved
            </p>
          </div>

          <div class="mt-4 flex items-center justify-center md:mt-0">
            <div class="flex space-x-8">
              <a v-for="item in footerNavigation.bottomLinks" :key="item.name" :href="item.href" class="text-sm text-gray-500 hover:text-gray-600">{{ item.name }}</a>
            </div>

            <div class="ml-6 border-l border-gray-200 pl-6">
              <a href="#" class="flex items-center text-gray-500 hover:text-gray-600">
                <img src="https://tailwindui.com/img/flags/flag-canada.svg" alt="" class="h-auto w-5 flex-shrink-0">
                <span class="ml-3 text-sm">Change</span>
                <span class="sr-only">location and currency</span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
