<script setup>
defineProps(["testimonial"]);
</script>

<template>
    <div
        class="flex w-full flex-col gap-2 bg-slate-200 p-6 transition-all duration-400 rounded-md cursor-pointer hover:scale-105 hover:opacity-100"
    >
        <div class="text-lg font-bold">{{ testimonial.title }}</div>
        <p class="text-sm text-gray-600">
            {{ testimonial.description }}
        </p>
        <div class="text-sm font-medium">- {{ testimonial.name }}</div>
    </div>
</template>

<style scoped></style>
