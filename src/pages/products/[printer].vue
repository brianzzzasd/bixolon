<script setup lang="ts">
import { StarIcon } from '@heroicons/vue/20/solid'
import { Tab, TabGroup, TabList, TabPanel, TabPanels } from '@headlessui/vue'

const props = defineProps<{ printer: string }>()

const printers = [
  {
    id: 1,
    name: 'SRP-S3000',
    description_1: '3-inch Linerless Printer',
    description_2: 'Feature-Rich',
    description_3: 'Premium',
    href: '#',
    imageSrc: '../../../public/printer_1.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 2,
    name: 'SRP-S300',
    description_1: '3 inch Re-Stick',
    description_2: 'Label and Receipt',
    description_3: 'Direct Thermal Printer',
    href: '#',
    imageSrc: '../../../public/printer_2.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 3,
    name: 'SRP-S200',
    description_1: '2-inch Direct Thermal',
    description_2: 'Linerless Printer',
    description_3: 'Compact and Economical',
    href: '#',
    imageSrc: '../../../public/printer_3.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 4,
    name: 'SRP-Q300',
    description_1: 'Smart and Flexible',
    description_2: '3 inch Cube',
    description_3: 'Printer for mPOS',
    href: '#',
    imageSrc: '../../../public/printer_4.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 5,
    name: 'SRP-S320',
    description_1: '3-inch',
    description_2: 'Linerless and Receipt',
    description_3: 'Ideal for use with electronic scales',
    href: '#',
    imageSrc: '../../../public/printer_5.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 6,
    name: 'SRP-Q200',
    description_1: 'Ultra Compact',
    description_2: '2-inch Cube',
    description_3: 'Direct Thermal Printer',
    href: '#',
    imageSrc: '../../../public/printer_6.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 7,
    name: 'SRP-350plusIII',
    description_1: 'The perfect fit for mPOS solutions',
    description_2: '3 inch Thermal',
    description_3: 'mPOS-ible Receipt Printer',
    href: '#',
    imageSrc: '../../../public/printer_7.jpeg',
    price: '$35',
    color: 'Black',
  },
  {
    id: 8,
    name: 'SRP-350III',
    description_1: 'The industry’s steady seller',
    description_2: '3 inch Thermal',
    description_3: 'Receipt Printer',
    href: '#',
    imageSrc: '../../../public/printer_8.jpeg',
    price: '$35',
    color: 'Black',
  },
]

const printer = printers.find((element) => {
  return element.id.toString() === props.printer
})

const product = {
  name: printer?.name,
  version: { name: '1.0', date: 'Jan 1, 2023', datetime: '2023-01-01' },
  price: '$220',
  description:
    'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo',
  highlights: [
    'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
    'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
    'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
  ],
  imageSrc: printer?.imageSrc,
  imageAlt: 'Sample of 30 icons with friendly and fun details in outline, filled, and brand color styles.',
}
const reviews = {
  average: 4,
  featured: [
    {
      id: 1,
      rating: 5,
      content: `
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit!</p>
      `,
      date: 'Dec 1, 2022',
      datetime: '2022-12-02',
      author: 'Emily Selman',
      avatarSrc:
        'https://images.unsplash.com/photo-1502685104226-ee32379fefbe?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80',
    },
    {
      id: 2,
      rating: 5,
      content: `
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit!</p>
      `,
      date: 'Dec 2, 2022',
      datetime: '2022-12-02',
      author: 'Hector Gibbons',
      avatarSrc:
        'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=256&h=256&q=80',
    },
    // More reviews...
  ],
}
const faqs = [
  {
    question: 'Lorem ipsum dolor sit amet?',
    answer:
      'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit',
  },
  {
    question: 'Lorem ipsum dolor sit amet?',
    answer:
      'Yes. The icons are drawn on a 24 x 24 pixel grid, but the icons can be scaled to different sizes as needed. We don\'t recommend going smaller than 20 x 20 or larger than 64 x 64 to retain legibility and visual balance.',
  },
]
const license = {
  href: '#',
  summary:
    'Lorem ipsum dolor sit amet, consectetur adipiscing elit',
  content: `
    <h4>Overview</h4>

    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit</p>

    <ul role="list">
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    </ul>

    <h4>What you can do with it</h4>

    <ul role="list">
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    </ul>

    <h4>What you can\'t do with it</h4>

    <ul role="list">
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    <li>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Lorem ipsum dolor sit amet, consectetur adipiscing elit</li>
    </ul>
  `,
}
</script>

<template>
  <div class="bg-white">
    <div class="mx-auto py-16 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
      <!-- Product -->
      <div class="lg:grid lg:grid-cols-7 lg:grid-rows-1 lg:gap-x-8 lg:gap-y-10 xl:gap-x-16">
        <!-- Product image -->
        <div class="lg:col-span-4 lg:row-end-1">
          <div class="aspect-w-4 aspect-h-3 overflow-hidden rounded-lg bg-white border border-gray-200">
            <img :src="product.imageSrc" :alt="product.imageAlt" class="object-cover object-center">
          </div>
        </div>

        <!-- Product details -->
        <div class="mx-auto mt-14 max-w-2xl sm:mt-16 lg:col-span-3 lg:row-span-2 lg:row-end-2 lg:mt-0 lg:max-w-none">
          <div class="flex flex-col-reverse">
            <div class="mt-4">
              <h1 class="text-2xl font-bold tracking-tight text-gray-900 sm:text-3xl">
                {{ product.name }}
              </h1>

              <h2 id="information-heading" class="sr-only">
                Product information
              </h2>
              <p class="mt-2 text-sm text-gray-500">
                Version {{ product.version.name }} (Updated <time :datetime="product.version.datetime">{{ product.version.date }}</time>)
              </p>
            </div>

            <div>
              <h3 class="sr-only">
                Reviews
              </h3>
              <div class="flex items-center">
                <StarIcon v-for="rating in [0, 1, 2, 3, 4]" :key="rating" class="h-5 w-5 flex-shrink-0" :class="[reviews.average > rating ? 'text-yellow-400' : 'text-gray-300']" aria-hidden="true" />
              </div>
              <p class="sr-only">
                {{ reviews.average }} out of 5 stars
              </p>
            </div>
          </div>

          <p class="mt-6 text-gray-500">
            {{ product.description }}
          </p>

          <div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-4 sm:grid-cols-2">
            <button type="button" class="flex w-full items-center justify-center rounded-md border border-transparent bg-brand-primary py-3 px-8 text-base font-medium text-white hover:opacity-75 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-50">
              Pay {{ product.price }}
            </button>
            <button type="button" class="flex w-full border border-gray-100 items-center justify-center rounded-md py-3 px-8 text-base font-medium text-gray-700 hover:opacity-75 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-50">
              Preview
            </button>
          </div>

          <div class="mt-10 border-t border-gray-200 pt-10">
            <h3 class="text-sm font-medium text-gray-900">
              Highlights
            </h3>
            <div class="prose prose-sm mt-4 text-gray-500">
              <ul role="list">
                <li v-for="highlight in product.highlights" :key="highlight">
                  {{ highlight }}
                </li>
              </ul>
            </div>
          </div>

          <div class="mt-10 border-t border-gray-200 pt-10">
            <h3 class="text-sm font-medium text-gray-900">
              License
            </h3>
            <p class="mt-4 text-sm text-gray-500">
              {{ license.summary }} <a :href="license.href" class="font-medium text-brand-primary hover:text-indigo-500">Read full license</a>
            </p>
          </div>

          <div class="mt-10 border-t border-gray-200 pt-10">
            <h3 class="text-sm font-medium text-gray-900">
              Share
            </h3>
            <ul role="list" class="mt-4 flex items-center space-x-6">
              <li>
                <a href="#" class="flex h-6 w-6 items-center justify-center text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Facebook</span>
                  <svg class="h-5 w-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd" d="M20 10c0-5.523-4.477-10-10-10S0 4.477 0 10c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V10h2.54V7.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V10h2.773l-.443 2.89h-2.33v6.988C16.343 19.128 20 14.991 20 10z" clip-rule="evenodd" />
                  </svg>
                </a>
              </li>
              <li>
                <a href="#" class="flex h-6 w-6 items-center justify-center text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Instagram</span>
                  <svg class="h-6 w-6" aria-hidden="true" fill="currentColor" viewBox="0 0 24 24">
                    <path fill-rule="evenodd" d="M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z" clip-rule="evenodd" />
                  </svg>
                </a>
              </li>
              <li>
                <a href="#" class="flex h-6 w-6 items-center justify-center text-gray-400 hover:text-gray-500">
                  <span class="sr-only">Share on Twitter</span>
                  <svg class="h-5 w-5" aria-hidden="true" fill="currentColor" viewBox="0 0 20 20">
                    <path d="M6.29 18.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0020 3.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.073 4.073 0 01.8 7.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 010 16.407a11.616 11.616 0 006.29 1.84" />
                  </svg>
                </a>
              </li>
            </ul>
          </div>
        </div>

        <div class="mx-auto mt-16 w-full max-w-2xl lg:col-span-4 lg:mt-0 lg:max-w-none">
          <TabGroup as="div">
            <div class="border-b border-gray-200">
              <TabList class="-mb-px flex space-x-8">
                <Tab v-slot="{ selected }" as="template">
                  <button class="whitespace-nowrap border-b-2 py-6 text-sm font-medium focus:outline-none" :class="[selected ? 'border-brand-primary text-brand-primary' : 'border-transparent text-gray-700 hover:text-gray-800 hover:border-gray-300']">
                    Customer Reviews
                  </button>
                </Tab>
                <Tab v-slot="{ selected }" as="template">
                  <button class="whitespace-nowrap border-b-2 py-6 text-sm font-medium focus:outline-none" :class="[selected ? 'border-brand-primary text-brand-primary' : 'border-transparent text-gray-700 hover:text-gray-800 hover:border-gray-300']">
                    FAQ
                  </button>
                </Tab>
                <Tab v-slot="{ selected }" as="template">
                  <button class="whitespace-nowrap border-b-2 py-6 text-sm font-medium focus:outline-none" :class="[selected ? 'border-brand-primary text-brand-primary' : 'border-transparent text-gray-700 hover:text-gray-800 hover:border-gray-300']">
                    License
                  </button>
                </Tab>
              </TabList>
            </div>
            <TabPanels as="template">
              <TabPanel class="-mb-10">
                <h3 class="sr-only">
                  Customer Reviews
                </h3>

                <div v-for="(review, reviewIdx) in reviews.featured" :key="review.id" class="flex space-x-4 text-sm text-gray-500">
                  <div class="flex-none py-10">
                    <img :src="review.avatarSrc" alt="" class="h-10 w-10 rounded-full bg-gray-100">
                  </div>
                  <div class="py-10" :class="[reviewIdx === 0 ? '' : 'border-t border-gray-200']">
                    <h3 class="font-medium text-gray-900">
                      {{ review.author }}
                    </h3>
                    <p>
                      <time :datetime="review.datetime">{{ review.date }}</time>
                    </p>

                    <div class="mt-4 flex items-center">
                      <StarIcon v-for="rating in [0, 1, 2, 3, 4]" :key="rating" class="h-5 w-5 flex-shrink-0" :class="[review.rating > rating ? 'text-yellow-400' : 'text-gray-300']" aria-hidden="true" />
                    </div>
                    <p class="sr-only">
                      {{ review.rating }} out of 5 stars
                    </p>

                    <div class="prose prose-sm mt-4 max-w-none text-gray-500" v-html="review.content" />
                  </div>
                </div>
              </TabPanel>

              <TabPanel class="text-sm text-gray-500">
                <h3 class="sr-only">
                  Frequently Asked Questions
                </h3>

                <dl>
                  <template v-for="faq in faqs" :key="faq.question">
                    <dt class="mt-10 font-medium text-gray-900">
                      {{ faq.question }}
                    </dt>
                    <dd class="prose prose-sm mt-2 max-w-none text-gray-500">
                      <p>{{ faq.answer }}</p>
                    </dd>
                  </template>
                </dl>
              </TabPanel>

              <TabPanel class="pt-10">
                <h3 class="sr-only">
                  License
                </h3>

                <div class="prose prose-sm max-w-none text-gray-500" v-html="license.content" />
              </TabPanel>
            </TabPanels>
          </TabGroup>
        </div>
      </div>
    </div>
  </div>
</template>
