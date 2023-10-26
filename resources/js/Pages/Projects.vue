<script setup>
import { ref } from "vue";
import "animate.css";

const animationClass = ref("animate__lightSpeedInLeft");
const DEFAULT_TECHNOLOGIES = [
    "HTML",
    "CSS",
    "JavaScript",
    "Vue.js",
    "Tailwind CSS",
];

const projects = ref([
    {
        id: 1,
        title: "Responsive Portfolio Website",
        description:
            " A personal portfolio website that showcases the web developer's skills, projects, and experiences. Built with a mobile-first approach, the site is fully responsive and adapts seamlessly across devices of varying screen sizes. The clean and modern design emphasizes user experience with smooth animations, interactive sections, and an intuitive navigation system. The site also integrates a blog section where the developer shares insights, tutorials, and updates. Leveraging the latest in web technologies, the portfolio site serves as a testament to the developer's front-end capabilities, attention to detail, and passion for creating compelling web experiences.",
        image: "/assets/project.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },
    {
        id: 2,
        title: "E-Commerce Platform",
        description:
            "A comprehensive online shopping platform designed to provide users with an unparalleled shopping experience. Features include advanced product search, user reviews, secure payment integration, and an intuitive admin dashboard for store management. The platform emphasizes speed and security, ensuring smooth user interactions and safe transactions.",
        image: "/assets/project.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },
    {
        id: 3,
        title: "Collaborative Task Manager",
        description:
            "A web-based application that allows teams to efficiently manage tasks and projects. With features like real-time collaboration, calendar integration, and customizable boards, teams can streamline workflows and improve productivity. The platform also offers integrations with popular tools like Slack and Google Drive, providing a centralized hub for all project-related activities.",
        image: "/assets/project.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },
    {
        id: 4,
        title: "Interactive Learning Platform",
        description:
            "An online learning portal catered to self-learners and educators alike. Users can browse a wide range of courses, watch video lectures, participate in quizzes, and earn certificates. Educators have the flexibility to upload content, manage students, and analyze course performance through detailed analytics.",
        image: "/assets/project.jpg",
        technologies: DEFAULT_TECHNOLOGIES,
    },
]);

const techColors = {
    HTML: "bg-red-400",
    CSS: "bg-blue-400",
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
        class="animate__animated flex flex-col space-y-6 p-8"
    >
        <div
            v-for="(project, index) in projects"
            :key="project.id"
            class="relative border rounded p-4 flex space-x-4"
        >
            <!-- For even indexed projects: Image on the right, Description on the left -->
            <template v-if="index % 2 === 0">
                <div class="flex flex-col w-3/4 text-start">
                    <h2 class="text-xl font-semibold">{{ project.title }}</h2>
                    <p>{{ project.description }}</p>
                    <div
                        class="absolute flex items-center left-0 bottom-0 w-3/4 mt-5 text-xs"
                    >
                        <ul class="flex pl-5 gap-2">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black px-2 py-1 rounded',
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
                    class="w-1/4 object-cover"
                />
            </template>

            <!-- For odd indexed projects: Image on the left, Description on the right -->
            <template v-else>
                <img
                    :src="project.image"
                    alt="Project Image"
                    class="w-1/4 object-cover"
                />
                <div class="flex flex-col w-3/4 h-32 pl-10">
                    <h2 class="text-xl font-semibold">{{ project.title }}</h2>
                    <p class="text-start">{{ project.description }}</p>
                    <div
                        class="absolute right-0 bottom-0 w-3/4 mt-5 text-xs text-right"
                    >
                        <ul class="flex pl-5 gap-2 justify-end">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black px-2 py-1 rounded',
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
