<script setup>
import "animate.css";
import { ref } from "vue";

const animationClass = ref("animate__zoomIn");

const releases = ref([
    {
        title: "HTML & CSS",
        description:
            "HTML is the standard markup language for Web pages. With HTML you can create your own Website. CSS is the language we use to style an HTML document. CSS describes how HTML elements should be displayed.",
        icon: "/assets/html.svg",
        isDark: false,
    },
    {
        title: "Tailwind CSS",
        description:
            "Tailwind CSS is basically a utility-first CSS framework for rapidly building custom user interfaces. It is a highly customizable, low-level CSS framework that gives you all of the building blocks you need to build bespoke designs without any annoying opinionated styles you have to fight to override.",
        badge: "Latest",
        icon: "assets/tailwind.svg",
        isDark: true,
    },
    {
        title: "JavaScript",
        description:
            "JavaScript is the Programming Language for the Web. JavaScript can update and change both HTML and CSS. JavaScript can calculate, manipulate and validate data.",
        icon: "assets/js.svg",
        isDark: true,
    },
    {
        title: "Vue.js",
        description:
            "Vue.js is an open-source model–view–viewmodel front end JavaScript framework for building user interfaces and single-page applications.",
        badge: "Latest",
        icon: "assets/vue.svg",
        isDark: true,
    },
    {
        title: "Bulma",
        description:
            "Bulma is a free, open source framework that provides ready-to-use frontend components that you can easily combine to build responsive web interfaces.",
        icon: "/assets/bulma.svg",
        isDark: true,
    },
    {
        title: "Laravel",
        description:
            "Laravel is a free, open-source PHP web framework intended for the development of web applications following the model–view–controller architectural pattern and based on Symfony.",
        badge: "Latest",
        icon: "/assets/laravel.svg",
        isDark: true,
    },
]);

// add about page to show my about me and my skills
</script>

<template>
    <div
        :class="animationClass"
        class="animate__animated items-start text-start mx-auto p-6 bg-white rounded-lg w-full flex flex-col"
    >
        <h1 class="text-4xl font-bold text-gray-800">About Me.</h1>
        <p class="mt-4 text-gray-600">
            As a software engineer, I specialize in merging creativity with
            technical expertise. Over the years, I've dedicated myself to
            crafting (and occasionally designing) exceptional web-based
            experiences. Every project, whether it's a responsive portfolio, an
            advanced betting platform, or an innovative interactive learning
            platform, showcases my commitment to quality, accessibility, and
            user-centric design.
        </p>

        <ol class="relative border-l mt-5 border-gray-200">
            <li
                v-for="(release, index) in releases"
                :key="index"
                class="mb-10 ml-6"
            >
                <img
                    :src="release.icon"
                    alt="Project Image"
                    class="absolute flex items-center justify-center w-8 h-8 bg-blue-100 rounded-full -left-3 ring-8 ring-white"
                />
                <h3
                    class="flex items-center mb-1 ml-2 text-lg font-semibold text-black"
                >
                    {{ release.title }}
                    <span
                        v-if="release.badge"
                        class="bg-blue-100 text-blue-800 text-sm font-medium mr-2 px-2.5 py-0.5 rounded ml-3"
                    >
                        {{ release.badge }}
                    </span>
                </h3>
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
