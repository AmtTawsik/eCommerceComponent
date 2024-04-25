<template>
    <div class="my-10">
        <OrderHistry :orders="orders" />
    </div>
</template>

<script setup>
const orders = [
    {
        orderNumber: "WU88191111",
        datePlaced: "Jul 6, 2021",
        totalAmount: 160.00,
        orderItems: [
            {
                discount: 10.00,
                deliveryDate: "July 12, 2021",
                product: {
                    name: "Micro Backpack",
                    description: "Are you a minimalist looking for a compact carry option? The Micro Backpack is the perfect size for your essential everyday carry items. Wear it like a backpack or carry it like a satchel for all-day use.",
                    price: 70.00,
                    img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-01.jpg",
                }
            },
            {
                discount: 10.00,
                deliveryDate: "July 12, 2021",
                product: {
                    name: "Nomad Shopping Tote",
                    description: "This durable shopping tote is perfect for the world traveler. Its yellow canvas construction is water, fray, tear resistant. The matching handle, backpack straps, and shoulder loops provide multiple carry options for a day out on your next adventure.",
                    price: 90.00,
                    img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-02.jpg",
                }
            },
        ]
    },
    {
        orderNumber: "WU88191111",
        datePlaced: "Jul 6, 2021",
        totalAmount: 160.00,
        orderItems: [
            {
                discount: 10.00,
                deliveryDate: "July 12, 2021",
                product: {
                    name: "Double Stack Clothing Bag",
                    description: "Save space and protect your favorite clothes in this double-layer garment bag. Each compartment easily holds multiple pairs of jeans or tops, while keeping your items neatly folded throughout your trip.",
                    price: 40.00,
                    img: "https://tailwindui.com/img/ecommerce-images/order-history-page-03-product-03.jpg",
                }
            },
        ]
    },
]
</script>

<style lang="scss" scoped></style>