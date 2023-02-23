<script setup>
const products = [
  {
    id: 1,
    name: 'SRP-S3000',
    description_1: '3-inch Linerless Printer',
    description_2: 'Feature-Rich',
    description_3: 'Premium',
    href: '/products/1',
    imageSrc: '../../../public/printer_1.jpeg',
  },
  {
    id: 2,
    name: 'SRP-S300',
    description_1: '3 inch Re-Stick',
    description_2: 'Label and Receipt',
    description_3: 'Direct Thermal Printer',
    href: '/products/2',
    imageSrc: '../../../public/printer_2.jpeg',
  },
  {
    id: 3,
    name: 'SRP-S200',
    description_1: '2-inch Direct Thermal',
    description_2: 'Linerless Printer',
    description_3: 'Compact and Economical',
    href: '/products/3',
    imageSrc: '../../../public/printer_3.jpeg',
  },
  {
    id: 4,
    name: 'SRP-Q300',
    description_1: 'Smart and Flexible',
    description_2: '3 inch Cube',
    description_3: 'Printer for mPOS',
    href: '/products/4',
    imageSrc: '../../../public/printer_4.jpeg',
  },
  {
    id: 5,
    name: 'SRP-S320',
    description_1: '3-inch',
    description_2: 'Linerless and Receipt',
    description_3: 'Ideal for use with electronic scales',
    href: '/products/5',
    imageSrc: '../../../public/printer_5.jpeg',
  },
  {
    id: 6,
    name: 'SRP-Q200',
    description_1: 'Ultra Compact',
    description_2: '2-inch Cube',
    description_3: 'Direct Thermal Printer',
    href: '/products/6',
    imageSrc: '../../../public/printer_6.jpeg',
  },
  {
    id: 7,
    name: 'SRP-350plusIII',
    description_1: 'The perfect fit for mPOS solutions',
    description_2: '3 inch Thermal',
    description_3: 'mPOS-ible Receipt Printer',
    href: '/products/7',
    imageSrc: '../../../public/printer_7.jpeg',
  },
  {
    id: 8,
    name: 'SRP-350III',
    description_1: 'The industry’s steady seller',
    description_2: '3 inch Thermal',
    description_3: 'Receipt Printer',
    href: '/products/8',
    imageSrc: '../../../public/printer_8.jpeg',
  },
]
</script>

<template>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl py-5 px-4 sm:py-10 sm:px-6 lg:max-w-7xl lg:px-8">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">
        Printers
      </h2>

      <div class="mt-6 grid grid-cols-1 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">
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
</template>
