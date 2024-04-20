<template>
    <div class="w-11/12 mx-auto">
        <UBreadcrumb class="my-5" divider="/" :links="product.breadcrumbs" />
        <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
            <section class="grid grid-cols-2 gap-5">
                <img class="col-span-2 rounded-xl" :src="product.images[0].src" alt="">
                <img class="rounded-xl md:block hidden" :src="product.images[1].src" alt="">
                <img class="rounded-xl md:block hidden" :src="product.images[2].src" alt="">
            </section>
            <section>
                <div class="flex justify-between">
                    <h3 class="text-2xl font-semibold">{{ product.name }}</h3>
                    <h3 class="text-2xl font-semibold">{{ product.price }}</h3>
                </div>
                <div class="flex mt-2">
                    <p>4.8</p>
                    <div class="flex items-center">
                        <svg class="w-4 h-4 text-yellow-300 ms-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            fill="currentColor" viewBox="0 0 22 20">
                            <path
                                d="M20.924 7.625a1.523 1.523 0 0 0-1.238-1.044l-5.051-.734-2.259-4.577a1.534 1.534 0 0 0-2.752 0L7.365 5.847l-5.051.734A1.535 1.535 0 0 0 1.463 9.2l3.656 3.563-.863 5.031a1.532 1.532 0 0 0 2.226 1.616L11 17.033l4.518 2.375a1.534 1.534 0 0 0 2.226-1.617l-.863-5.03L20.537 9.2a1.523 1.523 0 0 0 .387-1.575Z" />
                        </svg>
                        <svg class="w-4 h-4 text-yellow-300 ms-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            fill="currentColor" viewBox="0 0 22 20">
                            <path
                                d="M20.924 7.625a1.523 1.523 0 0 0-1.238-1.044l-5.051-.734-2.259-4.577a1.534 1.534 0 0 0-2.752 0L7.365 5.847l-5.051.734A1.535 1.535 0 0 0 1.463 9.2l3.656 3.563-.863 5.031a1.532 1.532 0 0 0 2.226 1.616L11 17.033l4.518 2.375a1.534 1.534 0 0 0 2.226-1.617l-.863-5.03L20.537 9.2a1.523 1.523 0 0 0 .387-1.575Z" />
                        </svg>
                        <svg class="w-4 h-4 text-yellow-300 ms-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            fill="currentColor" viewBox="0 0 22 20">
                            <path
                                d="M20.924 7.625a1.523 1.523 0 0 0-1.238-1.044l-5.051-.734-2.259-4.577a1.534 1.534 0 0 0-2.752 0L7.365 5.847l-5.051.734A1.535 1.535 0 0 0 1.463 9.2l3.656 3.563-.863 5.031a1.532 1.532 0 0 0 2.226 1.616L11 17.033l4.518 2.375a1.534 1.534 0 0 0 2.226-1.617l-.863-5.03L20.537 9.2a1.523 1.523 0 0 0 .387-1.575Z" />
                        </svg>
                        <svg class="w-4 h-4 text-yellow-300 ms-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                            fill="currentColor" viewBox="0 0 22 20">
                            <path
                                d="M20.924 7.625a1.523 1.523 0 0 0-1.238-1.044l-5.051-.734-2.259-4.577a1.534 1.534 0 0 0-2.752 0L7.365 5.847l-5.051.734A1.535 1.535 0 0 0 1.463 9.2l3.656 3.563-.863 5.031a1.532 1.532 0 0 0 2.226 1.616L11 17.033l4.518 2.375a1.534 1.534 0 0 0 2.226-1.617l-.863-5.03L20.537 9.2a1.523 1.523 0 0 0 .387-1.575Z" />
                        </svg>
                        <svg class="w-4 h-4 ms-1 text-gray-300" aria-hidden="true"
                            xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 22 20">
                            <path
                                d="M20.924 7.625a1.523 1.523 0 0 0-1.238-1.044l-5.051-.734-2.259-4.577a1.534 1.534 0 0 0-2.752 0L7.365 5.847l-5.051.734A1.535 1.535 0 0 0 1.463 9.2l3.656 3.563-.863 5.031a1.532 1.532 0 0 0 2.226 1.616L11 17.033l4.518 2.375a1.534 1.534 0 0 0 2.226-1.617l-.863-5.03L20.537 9.2a1.523 1.523 0 0 0 .387-1.575Z" />
                        </svg>
                    </div>
                    <p class="text-blue-500 ml-5">See all 512 reviews</p>
                </div>

                <form>
                    <h3 class="font-semibold mt-5">Color</h3>

                    <RadioGroup v-model="selectedColor" class="mt-2">
                        <RadioGroupLabel class="sr-only">Choose a color</RadioGroupLabel>
                        <div class="flex items-center space-x-3">
                            <RadioGroupOption as="template" v-for="color in product.colors" :key="color.name"
                                :value="color" v-slot="{ active, checked }">
                                <div
                                    :class="[color.selectedClass, active && checked ? 'ring ring-offset-1' : '', !active && checked ? 'ring-2' : '', 'relative -m-0.5 flex cursor-pointer items-center justify-center rounded-full p-0.5 focus:outline-none']">
                                    <RadioGroupLabel as="span" class="sr-only">{{ color.name }}</RadioGroupLabel>
                                    <span aria-hidden="true"
                                        :class="[color.class, 'h-8 w-8 rounded-full border border-black border-opacity-10']" />
                                </div>
                            </RadioGroupOption>
                        </div>
                    </RadioGroup>

                    <div class="mt-5">
                        <div class="flex items-center justify-between">
                            <h3 class="font-semibold">Size</h3>
                            <a href="#" class="text-sm font-medium text-indigo-600 hover:text-indigo-500">Size guide</a>
                        </div>

                        <RadioGroup v-model="selectedSize" class="mt-2">
                            <RadioGroupLabel class="sr-only">Choose a size</RadioGroupLabel>
                            <div class="grid grid-cols-4 gap-4 sm:grid-cols-8 lg:grid-cols-4">
                                <RadioGroupOption as="template" v-for="size in product.sizes" :key="size.name"
                                    :value="size" :disabled="!size.inStock" v-slot="{ active, checked }">
                                    <div
                                        :class="[size.inStock ? 'cursor-pointer bg-white text-gray-900 shadow-sm' : 'cursor-not-allowed bg-gray-50 text-gray-200', active ? 'ring-2 ring-indigo-500' : '', 'group relative flex items-center justify-center rounded-md border py-3 px-4 text-sm font-medium uppercase hover:bg-gray-50 focus:outline-none sm:flex-1 sm:py-6']">
                                        <RadioGroupLabel as="span">{{ size.name }}</RadioGroupLabel>
                                        <span v-if="size.inStock"
                                            :class="[active ? 'border' : 'border-2', checked ? 'border-indigo-500' : 'border-transparent', 'pointer-events-none absolute -inset-px rounded-md']"
                                            aria-hidden="true" />
                                        <span v-else aria-hidden="true"
                                            class="pointer-events-none absolute -inset-px rounded-md border-2 border-gray-200">
                                            <svg class="absolute inset-0 h-full w-full stroke-2 text-gray-200"
                                                viewBox="0 0 100 100" preserveAspectRatio="none" stroke="currentColor">
                                                <line x1="0" y1="100" x2="100" y2="0"
                                                    vector-effect="non-scaling-stroke" />
                                            </svg>
                                        </span>
                                    </div>
                                </RadioGroupOption>
                            </div>
                        </RadioGroup>
                    </div>

                    <button type="submit"
                        class="mt-10 flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Add
                        to cart</button>
                </form>
                <div class="mt-5">
                    <!-- Description -->
                    <h2 class="text-2xl font-semibold">Description</h2>
                    <p class="mt-2 text-gray-600 text-lg">{{ product.description }}</p>
                    <br>
                    <p class="text-gray-600 text-lg">{{ product.details }}</p>
                    <hr class="my-5">
                    <div class="mt-10">
                        <h3 class="text-2xl font-semibold">Fabric & Care</h3>

                        <div class="mt-4">
                            <ul role="list" class="list-disc space-y-2 pl-4">
                                <li v-for="highlight in product.highlights" :key="highlight" class="text-gray-400">
                                    <span class="text-gray-600">{{ highlight }}</span>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="grid grid-cols-1 md:grid-cols-2 mt-5 gap-5">
                        <div class="flex flex-col items-center border p-5 rounded-lg bg-[#F9FAFB]">
                            <UIcon name="i-heroicons-globe-alt" class="w-6 h-6 text-gray-600" />
                            <h6 class="text-lg font-semibold">International delivery</h6>
                            <p class="text-gray-600">Get your order in 2 days</p>
                        </div>
                        <div class="flex flex-col items-center border p-5 rounded-lg bg-[#F9FAFB]">
                            <UIcon name="i-heroicons-currency-dollar" class="w-6 h-6 text-gray-600" />
                            <h6 class="text-lg font-semibold">Loyalty rewards</h6>
                            <p class="text-gray-600">Don't look at other tees</p>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<script setup>
import { RadioGroup, RadioGroupLabel, RadioGroupOption } from '@headlessui/vue'

const product = {
    name: 'Basic Tee 6-Pack',
    price: '$192',
    href: '#',
    breadcrumbs: [
        { label: 'Women', to: '/' },
        { label: 'Clothing', to: '/' },
        { label: 'Basic Tee', to: '/' },
    ],
    images: [
        {
            src: 'https://tailwindui.com/img/ecommerce-images/product-page-01-featured-product-shot.jpg',
            alt: 'Two each of gray, white, and black shirts laying flat.',
        },
        {
            src: 'https://tailwindui.com/img/ecommerce-images/product-page-01-product-shot-01.jpg',
            alt: 'Model wearing plain black basic tee.',
        },
        {
            src: 'https://tailwindui.com/img/ecommerce-images/product-page-01-product-shot-02.jpg',
            alt: 'Model wearing plain gray basic tee.',
        },
        {
            src: 'https://tailwindui.com/img/ecommerce-images/product-page-02-featured-product-shot.jpg',
            alt: 'Model wearing plain white basic tee.',
        },
    ],
    colors: [
        { name: 'Black', class: 'bg-gray-900', selectedClass: 'ring-gray-900' },
        { name: 'White', class: 'bg-white', selectedClass: 'ring-gray-400' },
        { name: 'Gray', class: 'bg-gray-200', selectedClass: 'ring-gray-400' },
    ],
    sizes: [
        { name: 'XXS', inStock: false },
        { name: 'XS', inStock: true },
        { name: 'S', inStock: true },
        { name: 'M', inStock: true },
        { name: 'L', inStock: true },
        { name: 'XL', inStock: true },
        { name: '2XL', inStock: false },
        { name: '3XL', inStock: true },
    ],
    description:
        'The Basic Tee 6-Pack allows you to fully express your vibrant personality with three grayscale options. Feeling adventurous? Put on a heather gray tee. Want to be a trendsetter? Try our exclusive colorway: "Black". Need to add an extra pop of color to your outfit? Our white tee has you covered.',
    highlights: [
        'Only the best materials',
        'Ethically and locally made',
        'Pre-washed and pre-shrunk',
        'Machine wash cold with similar colors',
    ],
    details:
        'The 6-Pack includes two black, two white, and two heather gray Basic Tees. Sign up for our subscription service and be the first to get new, exciting colors, like our upcoming "Charcoal Gray" limited release.',
}
const reviews = { href: '#', average: 4, totalCount: 117 }

const selectedColor = ref(product.colors[0])
const selectedSize = ref(product.sizes[2])
</script>