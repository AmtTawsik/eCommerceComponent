<template>
    <div class="bg-[#F9FAFB]">
        <div class="w-11/12 mx-auto grid md:grid-cols-2 gap-5 md:gap-10 py-10">
            <section>
                <h4 class="text-xl font-semibold mb-4">Contact information</h4>
                <form>
                    <div class="mb-5">
                        <label for="email" class="block mb-2 text-sm font-medium text-gray-900">Your
                            email</label>
                        <input type="email" id="email"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <hr class="h-px my-8 bg-gray-200 border-0">
                    <h4 class="text-xl font-semibold mb-4">Shipping information</h4>
                    <div class="grid gap-4 sm:grid-cols-2 sm:gap-6 mb-5">
                        <div class="w-full">
                            <label for="name" class="block mb-2 text-sm font-medium text-gray-900">First
                                Name</label>
                            <input type="text" name="first_name" id="first_name"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                        <div class="w-full">
                            <label for="brand" class="block mb-2 text-sm font-medium text-gray-900">Last
                                Name</label>
                            <input type="text" name="last_name" id="last_name"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                    </div>
                    <div class="mb-5">
                        <label for="company"
                            class="block mb-2 text-sm font-medium text-gray-900">Company</label>
                        <input type="text" id="company"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <div class="mb-5">
                        <label for="address"
                            class="block mb-2 text-sm font-medium text-gray-900">Address</label>
                        <input type="text" id="address"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <div class="mb-5">
                        <label for="apartment"
                            class="block mb-2 text-sm font-medium text-gray-900">Apartment, suite,
                            etc.</label>
                        <input type="text" id="apartment"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <div class="grid gap-4 sm:grid-cols-2 sm:gap-6 mb-5">
                        <div class="w-full">
                            <label for="city"
                                class="block mb-2 text-sm font-medium text-gray-900">City</label>
                            <input type="text" name="city" id="city"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                        <div class="w-full">
                            <label for="country"
                                class="block mb-2 text-sm font-medium text-gray-900">Country</label>
                            <select
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                name="country" id="country">
                                <option value="United States">United States</option>
                                <option value="Canada">Canada</option>
                                <option value="India">India</option>
                            </select>
                        </div>
                    </div>
                    <div class="grid gap-4 sm:grid-cols-2 sm:gap-6 mb-5">
                        <div class="w-full">
                            <label for="state"
                                class="block mb-2 text-sm font-medium text-gray-900">State /
                                Province</label>
                            <input type="text" name="state" id="state"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                        <div class="w-full">
                            <label for="code"
                                class="block mb-2 text-sm font-medium text-gray-900">Postal code</label>
                            <input type="text" name="code" id="code"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                    </div>
                    <div class="mb-5">
                        <label for="phone"
                            class="block mb-2 text-sm font-medium text-gray-900">Phone</label>
                        <input type="number" id="phone"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <hr class="h-px my-8 bg-gray-200 border-0">
                    <h4 class="text-xl font-semibold mb-4">Delivery method</h4>
                    <ul class="grid w-full gap-6 md:grid-cols-2">
                        <li>
                            <input type="radio" v-model="delivery" id="hosting-small" name="hosting"
                                value="hosting-small" class="hidden peer" required />
                            <label for="hosting-small"
                                class="inline-flex items-center justify-between w-full p-3 text-black bg-white border border-gray-200 rounded-lg cursor-pointerhover:text-gray-300 peer-checked:border-blue-600 peer-checked:text-blue-600 hover:text-gray-600 hover:bg-gray-100">
                                <div class="block">
                                    <div class="w-full">Standard</div>
                                    <div class="w-full">4–10 business days</div>
                                    <p class="font-semibold mt-4">$5.00</p>
                                </div>
                                <svg v-if="delivery" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                                    fill="currentColor" class="w-6 h-6">
                                    <path fill-rule="evenodd"
                                        d="M2.25 12c0-5.385 4.365-9.75 9.75-9.75s9.75 4.365 9.75 9.75-4.365 9.75-9.75 9.75S2.25 17.385 2.25 12Zm13.36-1.814a.75.75 0 1 0-1.22-.872l-3.236 4.53L9.53 12.22a.75.75 0 0 0-1.06 1.06l2.25 2.25a.75.75 0 0 0 1.14-.094l3.75-5.25Z"
                                        clip-rule="evenodd" />
                                </svg>
                            </label>
                        </li>
                        <li>
                            <input type="radio" v-model="delivery" id="hosting-big" name="hosting" value="hosting-big"
                                class="hidden peer">
                            <label for="hosting-big"
                                class="inline-flex items-center justify-between w-full p-3 text-black bg-white border border-gray-200 rounded-lg cursor-pointer peer-checked:border-blue-600 peer-checked:text-blue-600 hover:text-gray-600 hover:bg-gray-100">
                                <div class="block">
                                    <div class="w-full">Express</div>
                                    <div class="w-full">3–5 business days</div>
                                    <p class="font-semibold mt-4">$15.00</p>
                                </div>
                                <svg v-if="delivery" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"
                                    fill="currentColor" class="w-6 h-6">
                                    <path fill-rule="evenodd"
                                        d="M2.25 12c0-5.385 4.365-9.75 9.75-9.75s9.75 4.365 9.75 9.75-4.365 9.75-9.75 9.75S2.25 17.385 2.25 12Zm13.36-1.814a.75.75 0 1 0-1.22-.872l-3.236 4.53L9.53 12.22a.75.75 0 0 0-1.06 1.06l2.25 2.25a.75.75 0 0 0 1.14-.094l3.75-5.25Z"
                                        clip-rule="evenodd" />
                                </svg>
                            </label>
                        </li>
                    </ul>
                    <hr class="h-px my-8 bg-gray-200 border-0">
                    <h4 class="text-xl font-semibold mb-4">Payment</h4>
                    <div class="flex mb-5">
                        <div class="flex items-center me-8">
                            <input id="inline-radio" type="radio" value="" name="inline-radio-group"
                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 focus:ring-2">
                            <label for="inline-radio"
                                class="ms-2 text-sm font-medium text-gray-900">Credit card</label>
                        </div>
                        <div class="flex items-center me-8">
                            <input id="inline-2-radio" type="radio" value="" name="inline-radio-group"
                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 focus:ring-2">
                            <label for="inline-2-radio"
                                class="ms-2 text-sm font-medium text-gray-900">PayPal</label>
                        </div>
                        <div class="flex items-center me-8">
                            <input checked id="inline-checked-radio" type="radio" value="" name="inline-radio-group"
                                class="w-4 h-4 text-blue-600 bg-gray-100 border-gray-300 focus:ring-blue-500 focus:ring-2">
                            <label for="inline-checked-radio"
                                class="ms-2 text-sm font-medium text-gray-900">eTransfer</label>
                        </div>
                    </div>
                    <div class="mb-5">
                        <label for="card" class="block mb-2 text-sm font-medium text-gray-900">Card number</label>
                        <input type="number" id="card"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>
                    <div class="mb-5">
                        <label for="card_name" class="block mb-2 text-sm font-medium text-gray-900">Name on card</label>
                        <input type="text" id="card_name"
                            class="border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 bg-white"
                            required />
                    </div>

                    <div class="grid gap-4 grid-cols-12 sm:gap-6 mb-5">
                        <div class="w-full col-span-9">
                            <label for="ex_date" class="block mb-2 text-sm font-medium text-gray-900">Expiration date (MM/YY)</label>
                            <input type="date" name="ex_date" id="ex_date"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                        <div class="w-full col-span-3">
                            <label for="cvc" class="block mb-2 text-sm font-medium text-gray-900">CVC</label>
                            <input type="number" name="cvc" id="cvc"
                                class="bg-white border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
                                required="">
                        </div>
                    </div>
                </form>
            </section>
            <section>
                <h4 class="text-xl font-semibold mb-4">Order summary</h4>
                <div class="border p-5 rounded-lg bg-white">
                    <template v-for="product in products">
                        <div class="mb-5 border-b pb-5">
                            <div class="flex gap-5">
                                <img class="md:w-48 w-28 rounded-md" :src="product.imageSrc" alt="">
                                <section class="w-full flex flex-col justify-between md:py-2">
                                    <div class="w-full flex justify-between">
                                        <div class="md:min-w-32">
                                            <h6>{{ product.name }}</h6>
                                            <p class="text-gray-600">{{ product.color }}</p>
                                            <p class="text-gray-600">{{ product.size }}</p>
                                        </div>
                                        <UIcon name="i-heroicons-trash"
                                            class="w-6 h-6 text-gray-600 md:mr-2 cursor-pointer" />
                                    </div>
                                    <div class="flex justify-between items-center">
                                        <p>{{ product.price }}</p>
                                        <div class="w-14">
                                            <USelectMenu v-model="selected" :options="people" />
                                        </div>
                                    </div>
                                </section>
                            </div>
                        </div>
                    </template>
                    <section class="col-span-5 h-fit p-5 bg-white">
                        <h6 class="text-xl font-medium">Order summary</h6>
                        <div class="flow-root">
                            <ul role="list" class="divide-y divide-gray-200">
                                <li class="py-3 sm:py-4">
                                    <div class="flex items-center">
                                        <div class="flex-1 min-w-0 ms-4">
                                            <p class="text-gray-500 truncate">
                                                Subtotal
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900">
                                            $99.00
                                        </div>
                                    </div>
                                </li>
                                <li class="py-3 sm:py-4">
                                    <div class="flex items-center ">
                                        <div class="flex-1 min-w-0 ms-4">
                                            <p class="text-gray-500 truncate">
                                                Shipping estimate
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900">
                                            $5.00
                                        </div>
                                    </div>
                                </li>
                                <li class="py-3 sm:py-4">
                                    <div class="flex items-center ">
                                        <div class="flex-1 min-w-0 ms-4">
                                            <p class="text-gray-500 truncate">
                                                Tax estimate
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900">
                                            $8.32
                                        </div>
                                    </div>
                                </li>
                                <li class="py-3 sm:py-4">
                                    <div class="flex items-center ">
                                        <div class="flex-1 min-w-0 ms-4">
                                            <p class="text-lg font-medium text-gray-900 truncate">
                                                Order total
                                            </p>
                                        </div>
                                        <div
                                            class="inline-flex items-center text-base font-semibold text-gray-900">
                                            $112.32
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </div>
                        <button type="submit"
                            class="mt-2 flex w-full items-center justify-center rounded-md border border-transparent bg-indigo-600 px-8 py-3 text-base font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2">Checkout
                            Now</button>
                    </section>
                </div>
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
    }
]

const people = [1, 2, 3, 4, 5, 6, 7, 8, 9]

const selected = ref(people[0])
const delivery = ref(null)
</script>