<script setup>
import { defineEmits, defineProps, ref, watch } from "vue";

const props = defineProps({
    options: Array,
    modelValue: String,
});

const emit = defineEmits(["update:modelValue"]);

const isOpen = ref(false);
const selected = ref(props.modelValue);

const toggleDropdown = () => (isOpen.value = !isOpen.value);

const selectOptionHandler = (option, event) => {
    event.stopPropagation();
    selectOption(option);
};

const selectOption = (option) => {
    selected.value = option;
    isOpen.value = false;
    emit("update:modelValue", option);
};

watch(
    () => props.modelValue,
    (newValue) => {
        selected.value = newValue;
    },
);
</script>

<template>
    <div
        class="relative border border-gray-300 rounded-md cursor-pointer bg-slate-200"
        @click="toggleDropdown"
    >
        <div
            class="flex justify-between items-center py-2 px-4 border-b border-gray-300"
        >
            {{ selected }}
            <svg
                :class="{ 'rotate-180': isOpen }"
                class="h-6 w-6 text-gray-600 transform transition-transform"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
            >
                <rect fill="none" height="24" width="24" x="0" />
                <g>
                    <path d="M7 10l5 5 5-5" />
                </g>
            </svg>
        </div>
        <div
            v-if="isOpen"
            class="absolute w-full bg-slate-100 z-10 rounded-md shadow-md"
        >
            <div
                v-for="option in options"
                :key="option"
                class="py-2 px-4 hover:bg-white rounded-b-md border-b border-gray-300"
                @click="selectOptionHandler(option, $event)"
            >
                {{ option }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.rotate-180 {
    transform: rotate(180deg);
}
</style>
