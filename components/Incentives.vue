<template>
    <div class="w-11/12 mx-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-5 items-center">
            <section class="md:hidden">
                <img class="rounded-xl" :src="incentives.picture" alt="">
            </section>
            <section>
                <h2 class="text-4xl font-bold w-10/12">{{ incentives.name }}</h2>
                <p class="text-lg text-gray-600 w-10/12 mt-5">{{ incentives.description }}</p>
            </section>
            <section class="hidden md:flex">
                <img class="rounded-xl" :src="incentives.picture" alt="">
            </section>
        </div>
        <div class="md:grid grid-cols-12 gap-5 mt-10">
            <template v-for="item in incentives.cards">
                <div class="col-span-3 mb-5">
                    <img :src="item.img" alt="">
                    <h5 class="my-2 text-lg font-semibold">{{ item.name }}</h5>
                    <p class="text-gray-600">{{ item.details }}</p>
                </div>
            </template>
        </div>
    </div>
</template>

<script setup>
const incentives = {
    name: 'We built our business on great customer service',
    description: 'At the beginning at least, but then we realized we could make a lot more money if we kinda stopped caring about that. Our new strategy is to write a bunch of things that look really good in the headlines, then clarify in the small print but hope people do not actually read it',
    picture: 'https://tailwindui.com/img/ecommerce-images/incentives-07-hero.jpg',
    cards: [
        {
            name: 'Free Shipping',
            details: "It's not actually free we just price it into the products. Someone's paying for it, and it's not us.",
            img: "https://tailwindui.com/img/ecommerce/icons/icon-delivery-light.svg"
        },
        {
            name: '24/7 Customer Support',
            details: "Our AI chat widget is powered by a naive series of if/else statements. Guaranteed to irritate.",
            img: "https://tailwindui.com/img/ecommerce/icons/icon-chat-light.svg"
        },
        {
            name: 'Fast Shopping Cart',
            details: "Look how fast that cart is going. What does this mean for the actual experience? I don't know.",
            img: "https://tailwindui.com/img/ecommerce/icons/icon-fast-checkout-light.svg"
        },
        {
            name: 'Gift Cards',
            details: "Buy them for your friends, especially if they don't like our store. Free money for us, it's great.",
            img: "https://tailwindui.com/img/ecommerce/icons/icon-gift-card-light.svg"
        }
    ],
}
</script>

<style lang="scss" scoped></style>