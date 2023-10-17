<template>
    <div class="flex w-full flex-col items-center h-screen">
        <div
            class="flex w-9/12 gap-20 items-center h-screen flex-col text-center p-20"
        >
            <div class="flex w-full items-center justify-between">
                <p class="text-2xl font-semibold">Home</p>
                <div class="space-x-4 font-semibold">
                    <a class="text-lg" href="#">Projects</a>
                    <a class="text-lg" href="#">About Me</a>
                    <a class="text-lg" href="#">Contact</a>
                </div>

                <div class="w-10 h-10">
                    <img
                        alt="BL Logo"
                        class="mx-auto w-10 h-10"
                        src="/assets/logo.png"
                    />
                </div>
            </div>

            <div class="flex w-full">
                <div class="flex-col gap-10 flex w-2/12">
                    <div class="mt-10">
                        <h1 class="text-4xl font-bold">Biniyam Lemma</h1>
                        <p class="text-xl mt-2 font-light">Web Developer</p>
                    </div>

                    <div class="flex mt-5 space-x-4">
                        <button
                            class="text-gray-900 bg-white border border-gray-300 focus:outline-none hover:bg-gray-100 focus:ring-4 focus:ring-gray-200 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-600 dark:focus:ring-gray-700"
                            type="button"
                        >
                            Something
                        </button>
                        <button
                            class="text-gray-900 bg-white border border-gray-300 focus:outline-none hover:bg-gray-100 focus:ring-4 focus:ring-gray-200 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-gray-800 dark:text-white dark:border-gray-600 dark:hover:bg-gray-700 dark:hover:border-gray-600 dark:focus:ring-gray-700"
                            type="button"
                        >
                            Resume(EN-US)
                        </button>
                    </div>
                </div>

                <div class="mt-10 w-8/12">
                    <img
                        alt="BL Logo"
                        class="mx-auto w-64 h-64"
                        src="/assets/logo.png"
                    />
                </div>
            </div>
            <div class="flex flex-col w-full justify-center mt-20">
                <h2 class="flex items-center justify-center font-bold text-4xl">
                    Follow me
                </h2>
                <div class="flex justify-center mt-5 space-x-4">
                    <a href="#">
                        <img
                            alt="BL Logo"
                            class="mx-auto w-20 h-20"
                            src="/assets/logo.png"
                        />
                    </a>
                    <a href="#">
                        <img
                            alt="BL Logo"
                            class="mx-auto w-20 h-20"
                            src="/assets/logo.png"
                        />
                    </a>
                    <a href="#">
                        <img
                            alt="BL Logo"
                            class="mx-auto w-20 h-20"
                            src="/assets/logo.png"
                        />
                    </a>
                    <a href="#">
                        <img
                            alt="BL Logo"
                            class="mx-auto w-20 h-20"
                            src="/assets/logo.png"
                        />
                    </a>
                </div>
            </div>
        </div>
        <div class="flex items-end mt-20 text-sm">
            <p>© 2023 - Developed by Biniyam Lemma</p>
            <p>v1.0.0</p>
        </div>
    </div>
</template>
<script setup></script>
