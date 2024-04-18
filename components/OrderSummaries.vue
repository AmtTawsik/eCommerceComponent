<template>
    <div class="md:grid grid-cols-2">
        <section>
            <img class="h-full" src="https://tailwindui.com/img/ecommerce-images/confirmation-page-06-hero.jpg" alt="">
        </section>
        <section class="p-10">
            <h6 class="text-blue-600">Payment successful</h6>
            <h1 class="text-3xl md:text-5xl font-bold my-2">Thanks for ordering</h1>
            <p class="text-gray-600 mb-5">We appreciate your order, we’re currently processing it. So hang tight and
                we’ll send you confirmation very soon!</p>
            <h6>Tracking number</h6>
            <h6 class="text-blue-600 mt-1 mb-5">{{ order.trakingNumber }}</h6>
            <hr class="">
            <template v-for="product in order.products">
                <div class="flex justify-between items-start border-b py-5">
                    <div class="flex">
                        <img class="w-24 rounded-lg mr-5" :src="product.img" alt="">
                        <div>
                            <h6 class="font-semibold">{{ product.name }}</h6>
                            <p class="text-gray-600">{{ product.color }}</p>
                            <p class="text-gray-600">{{ product.size }}</p>
                        </div>
                    </div>
                    <p class="font-semibold">${{ product.price }}</p>
                </div>
            </template>
            <div class="flex justify-between items-center mt-3">
                <p class="text-gray-600">Subtotal</p>
                <p class="font-semibold">$72.00</p>
            </div>
            <div class="flex justify-between items-center mt-3">
                <p class="text-gray-600">Shipping</p>
                <p class="font-semibold">$8.00</p>
            </div>
            <div class="flex justify-between items-center mt-3">
                <p class="text-gray-600">Taxes</p>
                <p class="font-semibold">$6.40</p>
            </div>
            <hr class="mt-3">
            <div class="flex justify-between items-center mt-3">
                <p class=" font-semibold">Taxes</p>
                <p class="font-bold">$86.40</p>
            </div>
            <div class="my-5 flex">
                <div class="md:mr-28 mr-5">
                    <p class="font-semibold mb-2">Shipping Address</p>
                    <p class="text-gray-600">Kristin Watson</p>
                    <p class="text-gray-600">7363 Cynthia Pass</p>
                    <p class="text-gray-600">Toronto, ON N3Y 4H8</p>
                </div>
                <div>
                    <p class="font-semibold mb-2">Payment Information</p>
                    <div class="flex">
                        <img class="w-10 h-10 mr-2" src="https://i.ibb.co/8gjP75d/visa.png" alt="">
                        <div>
                            <p class="text-gray-600">Ending with 4242</p>
                            <p class="text-gray-600">Expires 12 / 21</p>
                        </div>
                    </div>
                </div>
            </div>
            <hr class="mt-3">
            <div class="flex justify-end mt-5">
                <button class="text-[#224DBA] font-semibold">Continue Shopping →</button>
            </div>
        </section>
    </div>
</template>

<script setup>
const order = {
    trakingNumber: 51547878755545848512,
    products: [
        {
            name: "Basic Tee",
            color: "Charcoal",
            size: "L",
            price: 36,
            img: "https://tailwindui.com/img/ecommerce-images/confirmation-page-06-product-01.jpg"
        },
        {
            name: "Artwork Tee — Iso Dots",
            color: "Peach",
            size: "S",
            price: 36,
            img: "https://tailwindui.com/img/ecommerce-images/confirmation-page-06-product-02.jpg"
        },
    ]
}
</script>

<style lang="scss" scoped></style>