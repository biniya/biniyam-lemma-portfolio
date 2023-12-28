<script setup>
import { computed, ref } from "vue";

const props = defineProps({
    images: Array,
    title: String,
    show: Boolean,
});

const emit = defineEmits(["update:show"]);

const closeModal = () => {
    emit("update:show", false);
};

const currentImageIndex = ref(0);

const currentImage = computed(() => {
    if (props.images && props.images.length > 0) {
        return props.images[currentImageIndex.value];
    }
    return "";
});

const nextImage = () => {
    if (props.images && currentImageIndex.value < props.images.length - 1)
        currentImageIndex.value++;
};

const previousImage = () => {
    if (props.images && currentImageIndex.value > 0) currentImageIndex.value--;
};
</script>
<template>
    <div
        v-if="show"
        class="fixed inset-0 bg-transparent flex h-fit rounded-md pb-10 justify-center items-start pt-20"
    >
        <div class="relative bg-slate-200 p-10 rounded-lg max-w-4xl w-full">
            <div class="flex justify-between items-start mb-3">
                <h2 class="text-xl font-bold">{{ title }}</h2>
                <button
                    class="absolute top-0 right-0 pt-2 pr-4 text-black text-2xl font-semibold"
                    @click="closeModal"
                >
                    x
                </button>
            </div>
            <img
                :alt="title"
                :src="currentImage"
                class="w-full h-auto rounded"
            />
            <!-- Navigation buttons -->
            <div class="flex justify-center gap-4 mt-6">
                <button
                    v-if="currentImageIndex > 0"
                    class="mx-2 bg-white p-2 w-32 rounded-md"
                    @click="previousImage"
                >
                    Previous
                </button>
                <button
                    v-if="currentImageIndex < props.images.length - 1"
                    class="mx-2 bg-white p-2 w-32 rounded-md"
                    @click="nextImage"
                >
                    Next
                </button>
            </div>
        </div>
    </div>
</template>

<style scoped></style>
