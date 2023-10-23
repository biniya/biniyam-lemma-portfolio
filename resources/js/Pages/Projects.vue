<script setup>
import { ref } from "vue";
import "animate.css";

const animationClass = ref("animate__fadeInRightBig");

const projects = ref([
    {
        id: 1,
        image: "/assets/project.jpg",
        title: "Project 1",
        date: "2018",
        description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.",
    },
    {
        id: 2,
        image: "/assets/project.jpg",
        title: "Project 2",
        date: "2019",
        description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.",
    },
    {
        id: 3,
        image: "/assets/project.jpg",
        title: "Project 3",
        date: "2020",
        description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.",
    },
    {
        id: 4,
        image: "/assets/project.jpg",
        title: "Project 4",
        date: "2021",
        description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.",
    },
]);
</script>

<template>
    <div
        :class="animationClass"
        class="animate__animated grid grid-cols-3 gap-4 mt-12"
    >
        <h1 class="col-span-3 text-2xl font-bold text-start">My Projects</h1>

        <div
            v-for="project in projects"
            :key="project.id"
            class="h-40 w-full p-2 bg-white gap-2 rounded-lg shadow-lg flex"
        >
            <div class="flex justify-center">
                <img
                    :src="project.image"
                    alt="Project image"
                    class="max-w-full max-h-full object-cover rounded-md flex"
                />
                <div class="flex flex-col items-start justify-start text-start">
                    <h2 class="text-lg font-bold ml-3 underline">
                        {{ project.title }}
                    </h2>
                    <p class="text-sm ml-3 underline">{{ project.date }}</p>

                    <p class="flex text-sm ml-5 mt-2">
                        {{ project.description }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
