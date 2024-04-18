<template>
    <div class="w-11/12 mx-auto">
        <h2 class="text-3xl md:text-5xl font-bold mb-10">Shopping Cart</h2>
        <div class="md:grid grid-cols-12 gap-5 md:gap-10">
            <section class="col-span-7">
                <template v-for="product in products">
                    <div class="mb-5">
                        <hr class="h-px mb-5 bg-gray-200 border-0 dark:bg-gray-700">
                        <div class="flex gap-5">
                            <img class="w-48 rounded-md" :src="product.imageSrc" alt="">
                            <section class="w-full flex flex-col justify-between md:py-2">
                                <div class="w-full flex justify-between">
                                    <div class="md:min-w-32">
                                        <h6>{{ product.name }}</h6>
                                        <p class="text-gray-600">{{ product.color }} <span class="border-x ml-3 mr-4">
                                            </span> {{ product.size }}</p>
                                        <p>{{ product.price }}</p>
                                    </div>
                                    <USelectMenu class="hidden md:block" v-model="selected" :options="people" />
                                    <UIcon name="i-heroicons-x-mark" class="w-6 h-6 text-gray-600 md:mr-2 cursor-pointer" />
                                </div>
                                <div class="w-14">
                                    <USelectMenu class="md:hidden" v-model="selected" :options="people" />
                                </div>
                                <div>
                                    <p v-if="product.inStock" class="flex items-center">
                                        <UIcon name="i-heroicons-check" class="w-6 h-6 text-[#41CD75] mr-1" />
                                        <span>In stock</span>
                                    </p>
                                    <p v-else class="flex items-center">
                                        <UIcon name="i-heroicons-clock" class="w-6 h-6 text-gray-600 mr-1" />
                                        <span class="text-xs md:text-base">Ships in 3–4 weeks</span>
                                    </p>
                                </div>
                            </section>
                        </div>
                    </div>
                </template>
            </section>
            <section class="col-span-5 h-fit p-5 bg-[#F9FAFB]">
                <h6 class="text-xl font-medium">Order summary</h6>
                <div class="flow-root">
                    <ul role="list" class="divide-y divide-gray-200 dark:divide-gray-700">
                        <li class="py-3 sm:py-4">
                            <div class="flex items-center">
                                <div class="flex-1 min-w-0 ms-4">
                                    <p class="text-gray-500 truncate dark:text-gray-400">
                                        Subtotal
                                    </p>
                                </div>
                                <div
                                    class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                    $99.00
                                </div>
                            </div>
                        </li>
                        <li class="py-3 sm:py-4">
                            <div class="flex items-center ">
                                <div class="flex-1 min-w-0 ms-4">
                                    <p class="text-gray-500 truncate dark:text-gray-400">
                                        Shipping estimate
                                    </p>
                                </div>
                                <div
                                    class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                    $5.00
                                </div>
                            </div>
                        </li>
                        <li class="py-3 sm:py-4">
                            <div class="flex items-center ">
                                <div class="flex-1 min-w-0 ms-4">
                                    <p class="text-gray-500 truncate dark:text-gray-400">
                                        Tax estimate
                                    </p>
                                </div>
                                <div
                                    class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                    $8.32
                                </div>
                            </div>
                        </li>
                        <li class="py-3 sm:py-4">
                            <div class="flex items-center ">
                                <div class="flex-1 min-w-0 ms-4">
                                    <p class="text-lg font-medium text-gray-900 truncate dark:text-white">
                                        Order total
                                    </p>
                                </div>
                                <div
                                    class="inline-flex items-center text-base font-semibold text-gray-900 dark:text-white">
                                    $112.32
                                </div>
                            </div>
                        </li>
                    </ul>
                </div>
                <button type="submit"
                        class="mt-2 flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Checkout</button>
            </section>
        </div>
    </div>
</template>

<script setup>
const products = [
    {
        id: 1,
        name: 'Throwback Hip',
        href: '#',
        inStock: true,
        size: 'Large',
        color: 'Salmon',
        price: '$90.00',
        quantity: 1,
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-01.jpg',
        imageAlt: 'Salmon orange fabric pouch with match zipper, gray zipper pull, and adjustable hip belt.',
    },
    {
        id: 2,
        name: 'Medium Stuff',
        href: '#',
        inStock: false,
        size: 'Small',
        color: 'Blue',
        price: '$32.00',
        quantity: 1,
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-02.jpg',
        imageAlt:
            'Front of satchel with blue canvas body, black straps and handle, drawstring top, and front zipper pouch.',
    },
    {
        id: 3,
        name: 'Basic Set Tee',
        href: '#',
        inStock: true,
        size: 'Large',
        color: 'Blue',
        price: '$32.00',
        quantity: 1,
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-03.jpg',
        imageAlt:
            'Front of satchel with blue canvas body, black straps and handle, drawstring top, and front zipper pouch.',
    }
]

const people = [1, 2, 3, 4, 5, 6, 7, 8, 9]

const selected = ref(people[0])
</script>