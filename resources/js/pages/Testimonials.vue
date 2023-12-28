<script setup>
import { computed, ref } from "vue";
import TestimonialCard from "../components/TestimonialCard.vue";

const testimonials = ref([
    {
        id: 1,
        title: "General Manager",
        name: "Bereket Gobeze",
        description:
            "\"It was a pleasure to have Biniyam as a Web and Mobile Application Developer on our team at Anbessa Sports Betting. His collaboration with designers crafted user-friendly interfaces, and their full-stack development skills brought complex projects to successful completion with a keen eye for detail and security. Biniyam's work ethic and innovative approach have left a significant mark on our company's standards. We're confident they will excel in their future roles and recommend them highly.\"",
    },
    {
        id: 2,
        title: "Project Manager",
        name: "Kalid Abdu",
        description:
            "\"Biniyam's tenure as a Full-Stack Web Developer at Rigel Software Solutions has been marked by a seamless fusion of design and development. Mastering VueJs, Tailwind CSS, and JavaScript, as well as Laravel and database technologies like MySQL, Biniyam has delivered high-performance, user-friendly web applications. Their commitment to code excellence and strategic problem-solving elevated our projects beyond technical goals. Notably, Biniyam enhanced our front-end offerings with Vue.js, creating reactive, dynamic user interfaces that align perfectly with Laravel's back-end services.\"",
    },
    {
        id: 3,
        title: "COO",
        name: "Adil Abdu",
        description:
            '"Biniyam has been an invaluable asset to various projects, showcasing versatility and problem-solving prowess as a Full-Stack Developer. They\'ve successfully tackled diverse challenges, from minor fixes to constructing full-scale portfolios. With each task, Biniyam demonstrated technical agility and a keen eye for detail, ensuring each solution was not just a patch but an upgrade. Their portfolio work reflects a sophisticated understanding of user experience and design principles, resulting in polished, professional online representations for our clients."',
    },
    {
        id: 3,
        title: "CEO",
        name: "Yosef Seboka",
        description:
            '"Working across various projects, Biniyam has adeptly navigated the complexities of full-stack development, delivering bespoke solutions with precision. His expertise extends beyond routine tasks, addressing intricate problems with innovative strategies that transform challenges into seamless functionality. Biniyam has not only fixed issues but reimagined the possibilities of web presence, crafting portfolios that stand as testaments to their creative vision and technical acumen. The impact of his work is evident in the enhanced performance and refined aesthetic of every project he touch."',
    },
]);

// Visible testimonials in the carousel
const displayedTestimonials = computed(() => {
    const sortedTestimonials = [...testimonials.value];
    return sortedTestimonials;
});
</script>

<template>
    <div
        class="relative top-50 p-8 md:px-20 items-start text-start mx-auto gap-4 rounded-lg w-full flex flex-col h-screen"
    >
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-4 w-full">
            <!-- Sliding Testimonial Card -->
            <TestimonialCard
                v-for="(testimonial, index) in displayedTestimonials"
                :key="testimonial.id"
                :is-active="index === activeIndex"
                :testimonial="testimonial"
            />
        </div>
    </div>
</template>

<style></style>
