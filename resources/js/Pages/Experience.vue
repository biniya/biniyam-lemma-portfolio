<script setup>
import "animate.css";
import { ref } from "vue";

const animationClass = ref("animate__fadeInLeftBig");

const releases = ref([
    {
        title: "Flowbite Application UI v2.0.0",
        releaseDate: "January 13th, 2022",
        description:
            "Get access to over 20+ pages including a dashboard layout, charts, kanban board, calendar, and pre-order E-commerce & Marketing pages.",
        badge: "Latest",
        isDark: false,
    },
    {
        title: "Flowbite Figma v1.3.0",
        releaseDate: "December 7th, 2021",
        description:
            "All of the pages and components are first designed in Figma and we keep a parity between the two versions even as we update the project.",
        isDark: true,
    },
    {
        title: "Flowbite Library v1.2.2",
        releaseDate: "December 2nd, 2021",
        description:
            "Get started with dozens of web components and interactive elements built on top of Tailwind CSS.",
        isDark: true,
    },
]);
</script>

<template>
    <div
        :class="animationClass"
        class="animate__animated items-start text-start mx-auto mt-12 p-6 bg-white rounded-lg w-full flex flex-col"
    >
        <ol class="relative border-l border-gray-200">
            <li
                v-for="(release, index) in releases"
                :key="index"
                class="mb-10 ml-6"
            >
                <!-- ... remaining template, use 'release' to populate data -->
                <span
                    class="absolute flex items-center justify-center w-6 h-6 bg-blue-100 rounded-full -left-3 ring-8 ring-white"
                >
                    <svg
                        aria-hidden="true"
                        class="w-2.5 h-2.5 text-blue-800"
                        fill="currentColor"
                        viewBox="0 0 20 20"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M20 4a2 2 0 0 0-2-2h-2V1a1 1 0 0 0-2 0v1h-3V1a1 1 0 0 0-2 0v1H6V1a1 1 0 0 0-2 0v1H2a2 2 0 0 0-2 2v2h20V4ZM0 18a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8H0v10Zm5-8h10a1 1 0 0 1 0 2H5a1 1 0 0 1 0-2Z"
                        />
                    </svg>
                </span>
                <h3
                    class="flex items-center mb-1 text-lg font-semibold text-black"
                >
                    {{ release.title }}
                    <span
                        v-if="release.badge"
                        class="bg-blue-100 text-blue-800 text-sm font-medium mr-2 px-2.5 py-0.5 rounded ml-3"
                    >
                        {{ release.badge }}
                    </span>
                </h3>
                <time
                    class="block mb-2 text-sm font-normal leading-none text-gray-400 dark:text-gray-500"
                >
                    Released on {{ release.releaseDate }}
                </time>
                <p
                    class="mb-4 text-base font-normal text-gray-500 dark:text-gray-400"
                >
                    {{ release.description }}
                </p>
            </li>
        </ol>
    </div>
</template>

<style scoped></style>
