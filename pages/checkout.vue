<template>
    <div>
        <SopingCart :carts="carts" :people="people"/>
    </div>
</template>

<script setup>
const carts = {
    cartItem: [
        {
            quantity: 1,
            product: {
                id: 1,
                name: 'Throwback Hip',
                href: '#',
                inStock: true,
                size: 'Large',
                color: 'Salmon',
                price: '$90.00',
                imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-01.jpg',
                imageAlt: 'Salmon orange fabric pouch with match zipper, gray zipper pull, and adjustable hip belt.',
            }
        },
        {
            quantity: 1,
            product: {
                id: 2,
                name: 'Medium Stuff',
                href: '#',
                inStock: false,
                size: 'Small',
                color: 'Blue',
                price: '$32.00',
                imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-02.jpg',
                imageAlt: 'Front of canvas body, black handle, drawstring top, and front zipper pouch.',
            },
        },
        {
            quantity: 1,
            product: {
                id: 3,
                name: 'Basic Set Tee',
                href: '#',
                inStock: true,
                size: 'Large',
                color: 'Blue',
                price: '$32.00',
                imageSrc: 'https://tailwindui.com/img/ecommerce-images/shopping-cart-page-01-product-03.jpg',
                imageAlt: 'Front of satchel with blue canvas body, black straps and handle, drawstring top, and front zipper pouch.',
            }
        },
    ]
}

const people = [1, 2, 3, 4, 5, 6, 7, 8, 9]
</script>

<style lang="scss" scoped>

</style>