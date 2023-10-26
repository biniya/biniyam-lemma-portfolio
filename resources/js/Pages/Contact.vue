<script setup>
import { ref } from "vue";

const animationClass = ref("animate__zoomIn");
</script>

<template>
    <div :class="animationClass" class="animate__animated p-8">
        <h2 class="flex items-center justify-center font-bold text-4xl">
            Contact me
        </h2>
        <p
            class="flex items-center justify-center my-5 text-center text-sm text-gray-600"
        >
            I am currently open to freelance opportunities. Should you have a
            project in mind or require my expertise, please feel free to reach
            out.
        </p>

        <form action="#" class="mx-auto max-w-xl" method="POST">
            <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-2">
                <div>
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="first-name"
                        >First name</label
                    >
                    <div class="mt-2.5">
                        <input
                            id="first-name"
                            autocomplete="given-name"
                            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="first-name"
                            type="text"
                        />
                    </div>
                </div>
                <div>
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="last-name"
                        >Last name</label
                    >
                    <div class="mt-2.5">
                        <input
                            id="last-name"
                            autocomplete="family-name"
                            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="last-name"
                            type="text"
                        />
                    </div>
                </div>
                <div class="sm:col-span-2">
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="company"
                    >
                        <span>Company </span>
                        <span class="text-gray-500">(Optional)</span>
                    </label>
                    <div class="mt-2.5">
                        <input
                            id="company"
                            autocomplete="organization"
                            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="company"
                            type="text"
                        />
                    </div>
                </div>
                <div class="sm:col-span-2">
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="email"
                        >Email</label
                    >
                    <div class="mt-2.5">
                        <input
                            id="email"
                            autocomplete="email"
                            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="email"
                            type="email"
                        />
                    </div>
                </div>
                <div class="sm:col-span-2">
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="phone-number"
                        >Phone number</label
                    >
                    <div class="relative mt-2.5">
                        <span
                            class="absolute inset-y-0 left-0 flex items-center pl-3"
                        >
                            <span class="text-gray-500 sm:text-sm">+251</span>
                        </span>

                        <input
                            id="phone-number"
                            autocomplete="tel"
                            class="block w-full rounded-md border-0 px-3.5 py-2 pl-20 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="phone-number"
                            type="tel"
                        />
                    </div>
                </div>
                <div class="sm:col-span-2">
                    <label
                        class="block text-sm font-semibold leading-6 text-gray-900"
                        for="message"
                        >Message</label
                    >
                    <div class="mt-2.5">
                        <textarea
                            id="message"
                            class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                            name="message"
                            rows="4"
                        ></textarea>
                    </div>
                </div>
            </div>
            <div class="mt-10">
                <button
                    class="block w-full rounded-md bg-black px-3.5 py-2.5 text-center text-sm font-semibold text-white shadow-sm"
                    type="submit"
                >
                    Let's talk
                </button>
            </div>
        </form>
    </div>
</template>

<style scoped></style>
