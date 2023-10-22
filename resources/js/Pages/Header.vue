<script setup>
import Tab from "../Components/Tab.vue";
import { ref } from "vue";
import Projects from "./Projects.vue";
import About from "./About.vue";
import Contact from "./Contact.vue";
import Landing from "./Landing.vue";

const tabs = [
    { title: "Home" },
    { title: "Projects" },
    { title: "About" },
    { title: "Contact" },
];

const activeTab = ref("home");
</script>

<template>
    <div class="flex w-full items-center justify-center">
        <Tab v-model:active="activeTab" :tabs="tabs">
            <template #home>
                <Landing />
            </template>
            <template #projects>
                <Projects />
            </template>
            <template #about>
                <About />
            </template>
            <template #contact>
                <Contact />
            </template>
        </Tab>
    </div>
</template>

<style scoped></style>
