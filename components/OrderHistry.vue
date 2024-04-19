<template>
    <div class="md:w-10/12 w-11/12 mx-auto">
        <h3 class="text-3xl font-bold">Order history</h3>
        <p class="text-gray-600 mt-1">Check the status of recent orders, manage returns, and discover similar products.
        </p>
        <template v-for="order in orders">
            <div class="border rounded-lg mt-5">
                <section class="flex justify-between items-center md:px-10 px-2 py-4 border-b">
                    <div class="flex items-center gap-x-10">
                        <div>
                            <p>Order number</p>
                            <p class="text-gray-600">{{ order.orderNumber }}</p>
                        </div>
                        <div class="hidden md:block">
                            <p>Date placed</p>
                            <p class="text-gray-600">{{ order.datePlaced }}</p>
                        </div>
                        <div>
                            <p>Total amount</p>
                            <p>${{ order.totalAmount }}</p>
                        </div>
                    </div>
                    <div class="md:flex hidden items-center gap-x-5">
                        <UButton class="px-5 py-2" color="white" variant="solid">View Order</UButton>
                        <UButton class="px-5 py-2" color="white" variant="solid">View Invoice</UButton>
                    </div>
                    <button id="dropdownMenuIconButton" data-dropdown-toggle="dropdownDots"
                        class="md:hidden inline-flex items-center p-2 text-sm font-medium text-center text-gray-900 bg-white rounded-lg hover:bg-gray-100 focus:ring-4 focus:outline-none dark:text-white focus:ring-gray-50 dark:bg-gray-800 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
                        type="button">
                        <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor"
                            viewBox="0 0 4 15">
                            <path
                                d="M3.5 1.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 6.041a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 5.959a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                        </svg>
                    </button>

                    <!-- Dropdown menu -->
                    <div id="dropdownDots"
                        class="z-10 hidden bg-white divide-y divide-gray-100 rounded-lg shadow w-44 dark:bg-gray-700 dark:divide-gray-600">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200"
                            aria-labelledby="dropdownMenuIconButton">
                            <li>
                                <a href="#"
                                    class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">View Order</a>
                            </li>
                            <li>
                                <a href="#"
                                    class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">View Invoice</a>
                            </li>
                        </ul>
                    </div>
                </section>

                <template v-for="product in order.products">
                    <section class="border-t mb-4">
                        <div class="flex gap-x-5 p-5">
                            <img class="md:w-40 w-28 rounded-md" :src="product.img" :alt="product.name">
                            <div class="w-full">
                                <div class="w-full md:flex justify-between">
                                    <p class="font-semibold">{{ product.name }}</p>
                                    <p class="font-semibold">${{ product.price }}</p>
                                </div>
                                <p class="mt-2 hidden md:block">{{ product.description }}</p>
                            </div>
                        </div>
                        <div class="w-full md:flex justify-between items-center px-5 mt-2">
                            <p class="flex items-center gap-x-1">
                                <UIcon name="i-heroicons-check-circle" class="h-5 w-5 text-green-400"
                                    aria-hidden="true" />
                                Delivered on {{ product.deliveryDate }}
                            </p>
                            <div class="flex items-center justify-between md:justify-normal text-lg">
                                <p class="text-blue-600 hover:text-blue-700 cursor-pointer">View product</p>
                                <div class="border-l h-5 mx-4"></div>
                                <p class="text-blue-600 hover:text-blue-700 cursor-pointer">View product</p>
                            </div>
                        </div>
                    </section>
                </template>
            </div>
        </template>
    </div>
</template>

<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})

const orders = [
    {
        orderNumber: "WU88191111",
        datePlaced: "Jul 6, 2021",
        totalAmount: 160.00,
        products: [
            {
                name: "Micro Backpack",
                description: "Are you a minimalist looking for a compact carry option? The Micro Backpack is the perfect size for your essential everyday carry items. Wear it like a backpack or carry it like a satchel for all-day use.",
                price: 70.00,
                img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-01.jpg",
                deliveryDate: "July 12, 2021"
            },
            {
                name: "Nomad Shopping Tote",
                description: "This durable shopping tote is perfect for the world traveler. Its yellow canvas construction is water, fray, tear resistant. The matching handle, backpack straps, and shoulder loops provide multiple carry options for a day out on your next adventure.",
                price: 90.00,
                img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-02.jpg",
                deliveryDate: "July 12, 2021"
            },
        ]
    },
    {
        orderNumber: "AT48441546",
        datePlaced: "Dec 22, 2020",
        totalAmount: 40.00,
        products: [
            {
                name: "Double Stack Clothing Bag",
                description: "Save space and protect your favorite clothes in this double-layer garment bag. Each compartment easily holds multiple pairs of jeans or tops, while keeping your items neatly folded throughout your trip.",
                price: 40.00,
                img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-03.jpg",
                deliveryDate: "January 5, 2021"
            }
        ]
    }
]
</script>

<style lang="scss" scoped></style>