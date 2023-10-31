<script setup>
import { ref } from "vue";
import "animate.css";

const animationClass = ref("animate__zoomIn");
const DEFAULT_TECHNOLOGIES = [
    "JavaScript",
    "Vue.js",
    "Tailwind CSS",
    "Laravel",
    "Inertia.js",
];

const projects = ref([
    {
        id: 1,
        title: "Tutorial Platform",
        duration: "2019 - 2020",
        description:
            "Tutor, a web app that connects students of all ages and academic levels with highly skilled" +
            " tutors from a wide range of subjects. With its interface and robust features, Tutor is a one-stop " +
            "solution for all your tutoring needs. The platform offers a seamless experience for both students and " +
            "tutors, with a range of functionalities that make the process of learning and teaching a breeze.",
        image: "/assets/projects/tutor.png",
        technologies: DEFAULT_TECHNOLOGIES,
    },
    {
        id: 2,
        title: "Rigel School Management System",
        duration: "2020 - Present",
        description:
            "The Rigel School Management System, a flagship product from Rigel Studio, is poised to redefine the" +
            " landscape of education. With its innovative approach and a rich set of features, Rigel takes on the " +
            "challenges of the educational sector head-on. This cutting-edge platform offers an intuitive user " +
            "interface and a range of functionalities that promise to revolutionize teaching and learning.",
        image: "/assets/projects/sms.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },

    {
        id: 3,
        title: "Company Management System",
        duration: "2018 - 2019",
        description:
            "A web-based platform that allows companies to manage their employees, projects, and tasks. " +
            "The platform offers a seamless experience for both employees and managers, with a range of functionalities " +
            "that make the process of managing a company a smooth and hassle-free experience.",
        image: "/assets/projects/ankeboot.png",
        technologies: DEFAULT_TECHNOLOGIES,
    },
    {
        id: 4,
        title: "Bet+ Sport Betting Platform",
        duration: "2017 - 2018",
        description:
            "A web-based platform that allows users to bet on a wide range of sports. " +
            "The platform offers a seamless experience for both users and administrators, with a range of functionalities " +
            "that make the process of betting ultimately fun and exciting.",
        image: "/assets/projects/bet.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },
]);

const techColors = {
    "Inertia.js": "bg-red-400",
    Laravel: "bg-blue-400",
    JavaScript: "bg-yellow-400",
    "Vue.js": "bg-green-400",
    "Tailwind CSS": "bg-indigo-400",
    // Add other technologies and their colors as needed
};

function getColorForTech(tech) {
    return techColors[tech] || "bg-gray-500"; // Default to gray if technology is not in the list
}
</script>
<template>
    <div
        :class="animationClass"
        class="animate__animated flex flex-col space-y-6 p-8 md:px-20"
    >
        <div
            v-for="(project, index) in projects"
            :key="project.id"
            class="relative shadow rounded p-4 flex flex-col md:flex-row space-x-0 md:space-x-4 space-y-4 md:space-y-0"
        >
            <!-- For even indexed projects: Image on the right, Description on the left -->
            <template v-if="index % 2 === 0">
                <div
                    class="flex md:pt-0 pt-10 flex-col md:w-3/4 text-start w-full"
                >
                    <h2 class="text-lg md:text-xl font-semibold">
                        {{ project.title }}
                    </h2>
                    <time class="text-xs text-gray-500 underline">
                        {{ project.duration }}
                    </time>
                    <p class="text-sm md:text-base tracking-widest">
                        {{ project.description }}
                    </p>
                    <div
                        class="flex absolute items-center left-0 md:bottom-0 md:top-auto top-0 w-full md:w-3/4 mt-5 text-xs py-2"
                    >
                        <ul class="flex pl-5 gap-2">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black md:px-2 md:py-1 py-0 px-1 rounded',
                                ]"
                            >
                                {{ tech }}
                            </li>
                        </ul>
                    </div>
                </div>
                <img
                    :src="project.image"
                    alt="Project Image"
                    class="w-full md:w-1/4 object-cover mb-4 md:mb-0"
                />
            </template>

            <!-- For odd indexed projects: Image on the left, Description on the right -->
            <template v-else>
                <img
                    :src="project.image"
                    alt="Project Image"
                    class="w-full md:w-1/4 object-cover mb-4 md:mb-0 md:pt-0 pt-10"
                />
                <div class="flex md:pt-0 flex-col md:w-3/4 text-start w-full">
                    <h2 class="text-lg md:text-xl font-semibold">
                        {{ project.title }}
                    </h2>
                    <time class="text-xs text-gray-500 underline">
                        {{ project.duration }}
                    </time>
                    <p class="text-sm text-start md:text-base tracking-widest">
                        {{ project.description }}
                    </p>
                    <div
                        class="flex absolute items-center right-0 md:bottom-0 md:top-auto top-0 w-full md:w-3/4 mt-5 text-xs py-2"
                    >
                        <ul class="flex pl-5 gap-2 justify-end">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black md:px-2 md:py-1 py-0 px-1 rounded',
                                ]"
                            >
                                {{ tech }}
                            </li>
                        </ul>
                    </div>
                </div>
            </template>
        </div>
    </div>
</template>
