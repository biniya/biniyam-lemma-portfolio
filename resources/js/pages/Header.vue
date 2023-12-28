<script setup>
import Tab from "../components/Tab.vue";
import { ref } from "vue";
import Projects from "./Projects.vue";
// import Contact from "./Contact.vue";
import Landing from "./Landing.vue";
import About from "./About.vue";
import Testimonials from "./Testimonials.vue";

const tabs = [
    { title: "Home" },
    { title: "Projects" },
    { title: "About" },
    { title: "Testimonials" },
    // { title: "Contact" },
];

const activeTab = ref("Home");
</script>

<template>
    <div class="flex w-full z-50 items-center justify-center">
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
            <template #testimonials>
                <Testimonials />
            </template>
            <!--      <template #contact>-->
            <!--        <Contact />-->
            <!--      </template>-->
        </Tab>
    </div>
</template>

<style scoped></style>
