<script setup>
import { computed, ref } from "vue";
import "animate.css";
import DropDown from "../components/DropDown.vue";
import PhotoModal from "../components/PhotoModal.vue";

const animationClass = ref("animate__zoomIn");

const isModalVisible = ref(false);
const modalTitle = ref("");
const modalImages = ref([]);

const showModal = (project) => {
    modalTitle.value = project.title;
    modalImages.value =
        Array.isArray(project.subImages) && project.subImages.length > 0
            ? project.subImages
            : [project.image];
    isModalVisible.value = true;
};

const DEFAULT_TECHNOLOGIES = [
    "JavaScript",
    "Vue.js",
    "Tailwind CSS",
    "Laravel",
    "Inertia.js",
];

const projectCategories = ref({
    "Main Projects": "Main Projects",
    "Side Projects": "Side Projects",
});

const selectedCategory = ref("Main Projects");

const projects = ref([
    {
        id: 1,
        title: "Tutorial Platform",
        duration: "2019 - 2020",
        description:
            "Tutor, a web app that connects students of all ages and academic levels with highly skilled" +
            " tutors from a wide range of subjects. Tutor is a one-stop solution for all your tutoring needs. " +
            "The platform offers a seamless experience for both students and " +
            "tutors, with a range of functionalities that make the process of learning and teaching a breeze.",
        // image: "src/assets/projects/tutor.png",
        image: new URL("../assets/projects/tutor.png", import.meta.url).href,
        subImages: [
            new URL("../assets/projects/tutor/home_t.png", import.meta.url)
                .href,
            new URL(
                "../assets/projects/tutor/tutor_profile.png",
                import.meta.url,
            ).href,
            new URL(
                "../assets/projects/tutor/tutor_progress.png",
                import.meta.url,
            ).href,
            new URL(
                "../assets/projects/tutor/tutor_options.png",
                import.meta.url,
            ).href,
            new URL("../assets/projects/tutor/tutor_jobs.png", import.meta.url)
                .href,
        ],
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://saiph.rigel.studio",
    },
    {
        id: 2,
        title: "Rigel School Management System",
        duration: "2020 - Present",
        description:
            "The Rigel School Management System, a flagship product from Rigel Studio, is poised to redefine the" +
            " landscape of education. With its innovative approach and a rich set of features," +
            " This cutting-edge platform offers an intuitive user " +
            "interface and a range of functionalities that promise to revolutionize teaching and learning.",
        // image: "src/assets/projects/sms.jpg",
        image: new URL("../assets/projects/sms.jpg", import.meta.url).href,
        subImages: [
            new URL("../assets/projects/sms/SMS_Login.png", import.meta.url)
                .href,
            new URL("../assets/projects/sms/Announcement.png", import.meta.url)
                .href,
            new URL(
                "../assets/projects/sms/School_Schedule.png",
                import.meta.url,
            ).href,
            new URL("../assets/projects/sms/Settings.png", import.meta.url)
                .href,
            new URL("../assets/projects/sms/TimeTable.png", import.meta.url)
                .href,
            new URL(
                "../assets/projects/sms/Teachers_MyClass.png",
                import.meta.url,
            ).href,
            new URL(
                "../assets/projects/sms/Teachers_Schedule.png",
                import.meta.url,
            ).href,
            new URL("../assets/projects/sms/Mark_Students.png", import.meta.url)
                .href,
            new URL("../assets/projects/sms/LessonPlan.png", import.meta.url)
                .href,
        ],
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://demo.rigel.studio",
    },

    {
        id: 3,
        title: "Company Management System",
        duration: "2018 - 2019",
        description:
            "A web-based platform that allows companies to manage their employees, projects, and tasks. " +
            "The platform offers a seamless experience for both employees and managers, with a range of functionalities " +
            "that make the process of managing a company a smooth and hassle-free experience.",
        // image: "src/assets/projects/ankeboot.png",
        image: new URL("../assets/projects/ankeboot.png", import.meta.url).href,
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://www.ankeboot.com/",
    },
    {
        id: 4,
        title: "Bet+ Sport Betting Platform",
        duration: "2017 - 2018",
        description:
            "A web-based platform that allows users to bet on a wide range of sports. " +
            "The platform offers a seamless experience for both users and administrators, with a range of functionalities " +
            "that make the process of betting ultimately fun and exciting.",
        // image: "src/assets/projects/bet.png",
        image: new URL("../assets/projects/bet.png", import.meta.url).href,
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://www.betplus.et/",
    },
]);

const sideProjects = ref([
    {
        id: 1,
        title: "Biniyam's Portfolio",
        duration: "2021 - Present",
        description:
            "Welcome to my digital realm, a vibrant showcase of my journey as a developer and designer." +
            "Here, you'll find a curated collection of my projects, each a testament to my passion for creating elegant and efficient solutions," +
            "My portfolio is not just a reflection of my technical proficiency but a window into my creative process and problem-solving capabilities.",
        // image: "src/assets/projects/portfolio.png",
        image: new URL("../assets/projects/portfolio.png", import.meta.url)
            .href,
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://biniyam.vercel.app/",
    },
    {
        id: 2,
        title: "Wordle | Tic Tac Toe - Interactive Learning Platform",
        duration: "2021 - Present",
        description:
            "Discover the magic of Wordel, a web-based platform where language learning meets fun and engagement. " +
            "Immerse yourself in tailored games and challenges that adapt to your pace and style. " +
            "With each click, journey closer to mastery in a world where every word is an adventure.",
        // image: "src/assets/projects/wordle.png",
        image: new URL("../assets/projects/wordle.png", import.meta.url).href,
        technologies: DEFAULT_TECHNOLOGIES,
        link: "https://https-github-com-biniyam-wordle.vercel.app/",
    },
]);

const filteredProjects = computed(() => {
    return selectedCategory.value === "Main Projects"
        ? projects.value
        : sideProjects.value;
});

const techColors = {
    "Inertia.js": "border-red-400",
    Laravel: "border-blue-400",
    JavaScript: "border-yellow-400",
    "Vue.js": "border-green-400",
    "Tailwind CSS": "border-indigo-400",
    // Add other technologies and their colors as needed
};

function getColorForTech(tech) {
    return techColors[tech] || "bg-gray-400"; // Default to gray if technology is not in the list
}
</script>
<template>
    <div
        class="animate__animated animate__fadeOutUp fixed justify-center items-center w-full flex"
    >
        <span class="text-4xl md:text-4xl font-bold text-center"
            >My Projects</span
        >
    </div>
    <div
        :class="animationClass"
        class="animate__animated flex flex-col space-y-6 p-8 min-h-screen md:px-20 mx-auto md:mx-32 overflow-hidden"
    >
        <div class="flex justify-between items-center">
            <h1 class="text-3xl md:text-4xl font-bold text-gray-800">
                My Projects
            </h1>
            <DropDown
                v-model:modelValue="selectedCategory"
                :options="projectCategories"
            />
        </div>
        <div
            v-for="(project, index) in filteredProjects"
            :key="project.id"
            class="relative shadow rounded p-3 flex flex-col md:flex-row space-x-0 md:space-x-4 space-y-3 md:space-y-0"
        >
            <!-- For even indexed projects: Image on the right, Description on the left -->
            <template v-if="index % 2 === 0">
                <div class="flex flex-col md:w-3/4 text-start w-full">
                    <h2 class="flex gap-4 text-lg md:text-xl font-semibold">
                        <span>{{ project.title }}</span>
                        <a :href="project.link" target="_blank">
                            <svg
                                class="feather feather-external-link"
                                fill="none"
                                height="24"
                                stroke="blue"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                viewBox="0 0 24 24"
                                width="24"
                                xmlns="http://www.w3.org/2000/svg"
                            >
                                <path
                                    d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                                ></path>
                                <polyline points="15 3 21 3 21 9"></polyline>
                                <line x1="10" x2="21" y1="14" y2="3"></line>
                            </svg>
                        </a>
                    </h2>
                    <time class="text-xs text-gray-500 underline">
                        {{ project.duration }}
                    </time>
                    <p class="text-sm md:text-base tracking-widest">
                        {{ project.description }}
                    </p>
                    <div
                        class="hidden md:flex absolute items-center md:bottom-0 md:top-auto w-full md:w-3/4 mt-5 text-xs py-2"
                    >
                        <ul class="flex pl-5 gap-2">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black md:px-2 md:py-1 py-0 px-1 rounded-md border-2',
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
                    class="w-full md:w-1/4 object-cover mb-4 md:mb-0 cursor-pointer"
                    @click="showModal(project)"
                />
                <PhotoModal
                    :images="modalImages"
                    :show="isModalVisible"
                    :title="modalTitle"
                    @update:show="isModalVisible = $event"
                />
            </template>

            <!-- For odd indexed projects: Image on the left, Description on the right -->
            <template v-else>
                <div class="flex md:pt-0 flex-col md:w-3/4 text-start w-full">
                    <h2 class="flex gap-4 text-lg md:text-xl font-semibold">
                        <span>{{ project.title }}</span>
                        <a :href="project.link" target="_blank">
                            <svg
                                class="feather feather-external-link"
                                fill="none"
                                height="24"
                                stroke="blue"
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                viewBox="0 0 24 24"
                                width="24"
                                xmlns="http://www.w3.org/2000/svg"
                            >
                                <path
                                    d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                                ></path>
                                <polyline points="15 3 21 3 21 9"></polyline>
                                <line x1="10" x2="21" y1="14" y2="3"></line>
                            </svg>
                        </a>
                    </h2>
                    <time class="text-xs text-gray-500 underline">
                        {{ project.duration }}
                    </time>
                    <p class="text-sm text-start md:text-base tracking-widest">
                        {{ project.description }}
                    </p>
                    <div
                        class="hidden md:flex absolute items-center md:bottom-0 md:top-auto w-full md:w-3/4 mt-5 text-xs py-2"
                    >
                        <ul class="flex pl-5 gap-2 justify-end">
                            <li
                                v-for="tech in project.technologies"
                                :key="tech"
                                :class="[
                                    getColorForTech(tech),
                                    'text-black md:px-2 md:py-1 py-0 px-1 rounded-md border-2',
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
                    class="w-full md:w-1/4 object-cover mb-4 md:mb-0 cursor-pointer"
                    @click="showModal(project)"
                />
                <PhotoModal
                    :images="modalImages"
                    :show="isModalVisible"
                    :title="modalTitle"
                    @update:show="isModalVisible = $event"
                />
            </template>
        </div>
    </div>
</template>
