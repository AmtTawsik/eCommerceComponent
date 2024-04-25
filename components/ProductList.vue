<template>
    <div class="bg-white">
        <div>
            <div class="flex justify-between items-center mx-auto w-11/12">
                <h2 class="md:text-2xl text-sm font-bold tracking-tight text-gray-900">Trending products</h2>
                <p class="text-blue-600 md:text-lg text-xs font-bold cursor-pointer">Shop the collection →</p>
            </div>
            <Products :products="products" />
        </div>
    </div>
</template>

<script setup>
const products = [
    {
        id: 1,
        name: 'Basic Tee',
        href: '#',
        imageSrc: 'https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-01.jpg',
        imageAlt: "Front of men's Basic Tee in black.",
        price: '$35',
        color: 'Black',
    },
    {
        "id": 2,
        "name": "Casual Shirt",
        "href": "#",
        "imageSrc": "https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-02.jpg",
        "imageAlt": "Front of men's Casual Shirt in blue.",
        "price": "$45",
        "color": "Blue"
    },
    {
        "id": 3,
        "name": "Denim Jeans",
        "href": "#",
        "imageSrc": "https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-03.jpg",
        "imageAlt": "Front of men's Denim Jeans in dark wash.",
        "price": "$55",
        "color": "Dark Wash"
    },
    {
        "id": 4,
        "name": "Classic Hoodie",
        "href": "#",
        "imageSrc": "https://tailwindui.com/img/ecommerce-images/product-page-01-related-product-04.jpg",
        "imageAlt": "Front of men's Classic Hoodie in gray.",
        "price": "$65",
        "color": "Gray"
    },
    {
        "id": 5,
        "name": "Athletic Shorts",
        "href": "#",
        "imageSrc": "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg",
        "imageAlt": "Front of men's Athletic Shorts in black.",
        "price": "$30",
        "color": "Black"
    },
    {
        "id": 6,
        "name": "Leather Belt",
        "href": "#",
        "imageSrc": "https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-02.jpg",
        "imageAlt": "Men's Leather Belt in brown.",
        "price": "$25",
        "color": "Brown"
    },
    {
        "id": 7,
        "name": 'Focus Paper Refill',
        "href": '#',
        "price": '$89',
        "imageSrc": 'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-03.jpg',
        "imageAlt": 'Person using a pen to cross a task off a productivity paper card.',
        "color": "Dark Wash"
    },
    {
        "id": 8,
        "name": 'Machined Mechanical Pencil',
        "href": '#',
        "price": '$35',
        "imageSrc": 'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-04.jpg',
        "imageAlt": 'Hand holding black machined steel mechanical pencil with brass tip and top.',
        "color": "Black"
    },
]
</script>