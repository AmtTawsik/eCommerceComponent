<template>
    <div class="bg-white">
        <div class="mx-auto w-11/12">
            <div class="mt-6 grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">
                <div v-for="product in products" :key="product.id" class="group relative">
                    <div
                        class="aspect-h-1 aspect-w-1 w-full overflow-hidden rounded-md bg-gray-200 lg:aspect-none group-hover:opacity-75 lg:h-80">
                        <img :src="product.imageSrc" :alt="product.imageAlt"
                            class="h-full w-full object-cover object-center lg:h-full lg:w-full" />
                    </div>
                    <div class="mt-4 flex justify-between">
                        <div>
                            <h3 class="text-sm text-gray-700">
                                <a :href="product.href">
                                    <span aria-hidden="true" class="absolute inset-0" />
                                    {{ product.name }}
                                </a>
                            </h3>
                            <p class="mt-1 text-sm text-gray-500">{{ product.color }}</p>
                        </div>
                        <p class="text-sm font-medium text-gray-900">{{ product.price }}</p>
                    </div>
                    <button type="submit"
                        class="mt-2 flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Add
                        to cart</button>
                </div>
            </div>
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