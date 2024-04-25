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
                        class="md:hidden inline-flex items-center p-2 text-sm font-medium text-center text-gray-900 bg-white rounded-lg hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-gray-50"
                        type="button">
                        <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor"
                            viewBox="0 0 4 15">
                            <path
                                d="M3.5 1.5a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 6.041a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Zm0 5.959a1.5 1.5 0 1 1-3 0 1.5 1.5 0 0 1 3 0Z" />
                        </svg>
                    </button>

                    <!-- Dropdown menu -->
                    <div id="dropdownDots" class="z-10 hidden bg-white divide-y divide-gray-100 rounded-lg shadow w-44">
                        <ul class="py-2 text-sm text-gray-700" aria-labelledby="dropdownMenuIconButton">
                            <li>
                                <a href="#" class="block px-4 py-2 hover:bg-gray-100">View Order</a>
                            </li>
                            <li>
                                <a href="#" class="block px-4 py-2 hover:bg-gray-100">View Invoice</a>
                            </li>
                        </ul>
                    </div>
                </section>
                
                <template v-for="data in order.orderItems">
                    <section class="border-t mb-4">
                        <div class="flex gap-x-5 p-5">
                            <img class="md:w-40 w-28 rounded-md" :src="data.product.img" :alt="data.product.name">
                            <div class="w-full">
                                <div class="w-full md:flex justify-between">
                                    <p class="font-semibold">{{ data.product.name }}</p>
                                    <p class="font-semibold">${{ data.product.price }}</p>
                                </div>
                                <p class="mt-2 hidden md:block">{{ data.product.description }}</p>
                            </div>
                        </div>
                        <div class="w-full md:flex justify-between items-center px-5 mt-2">
                            <p class="flex items-center gap-x-1">
                                <UIcon name="i-heroicons-check-circle" class="h-5 w-5 text-green-400"
                                    aria-hidden="true" />
                                Delivered on {{ order.datePlaced }}
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

const { orders } = defineProps(["orders"]);
</script>

<style lang="scss" scoped></style>