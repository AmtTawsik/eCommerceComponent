<template>
    <div class="relative bg-gray-100">
        <div class="mx-auto w-11/12">
            <div class="mx-auto max-w-2xl py-16 sm:py-24 lg:max-w-none lg:py-32">
                <div class="flex justify-between items-center">
                    <h2 class="md:text-2xl text-sm font-bold tracking-tight text-gray-900">Shop by Category</h2>
                    <p class="text-blue-600 md:text-lg text-xs font-bold cursor-pointer">Browse all categories →</p>
                </div>

                <div class="mt-6 space-y-12 lg:grid lg:grid-cols-5 lg:gap-x-6 lg:space-y-0">
                    <div v-for="callout in callouts" :key="callout.name" class="group relative">
                        <div
                            class="relative grid h-[20rem] w-full flex-col items-end justify-center overflow-hidden rounded-xl bg-white bg-clip-border text-center text-gray-700 cursor-pointer">
                            <div :style="{ 'background-image': `url('${callout.imageSrc}')` }"
                                class="absolute inset-0 m-0 h-full w-full overflow-hidden rounded-none bg-transparent bg-cover bg-clip-border bg-center text-gray-700 shadow-none">
                                <div
                                    class="absolute inset-0 w-full h-full to-bg-black-10 bg-gradient-to-t from-black/80 via-black/50">
                                </div>
                            </div>
                            <div class="absolute bottom-2 left-2">
                                <h2 class="mb-2  font-sans text-xl font-medium  text-white  text-start">
                                    {{ callout.name }}
                                </h2>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const callouts = [
    {
        name: 'Desk and Office',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/home-page-01-category-01.jpg',
        imageAlt: 'Desk with leather desk pad, walnut desk organizer, wireless keyboard and mouse, and porcelain mug.',
        href: '#',
    },
    {
        name: 'Home Decor',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/home-page-01-category-02.jpg',
        imageAlt: 'Various decorative items for home decor.',
        href: '#',
    },
    {
        name: 'Outdoor Living',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/home-page-01-category-03.jpg',
        imageAlt: 'Outdoor gear including tents, sleeping bags, and cooking equipment.',
        href: '#',
    },
    {
        name: 'Fitness and Wellness',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/home-page-01-category-04.jpg',
        imageAlt: 'Fitness equipment including yoga mats, weights, and resistance bands.',
        href: '#',
    },
    {
        name: 'Technology',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/home-page-01-category-05.jpg',
        imageAlt: 'Latest technology products including smartphones, laptops, and headphones.',
        href: '#',
    },
]
</script>
