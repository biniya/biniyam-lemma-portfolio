<script setup>
import { defineEmits, defineProps, ref, toRefs, watch } from "vue";
import { Tab, TabGroup, TabList } from "@headlessui/vue";
import Home from "../Pages/Home.vue";

const emit = defineEmits();
const props = defineProps({
    tabs: {
        type: Array,
        required: true,
    },
    active: {
        type: [String, Number],
        default: "Home",
    },
    activeOnly: {
        type: Boolean,
        default: false,
    },
});

// Initialize currentActiveTab with props.active
const currentActiveTab = ref(props.active.toLowerCase());

watch(currentActiveTab, (newActive) => {
    emit("update:active", newActive);
});

// Function to update the active tab
const updateActiveTab = (tabName) => {
    currentActiveTab.value = tabName.toLowerCase();
};

const { tabs, active } = toRefs(props);

watch(active, (newActive) => {
    emit("update:active", newActive);
});
</script>

<template>
    <div class="flex w-full flex-col items-center justify-center">
        <TabGroup v-slot="{ selectedIndex }">
            <!-- Buttons -->
            <div class="flex justify-center items-center w-full">
                <TabList
                    class="flex flex-wrap items-start justify-center bg-slate-200 w-4/12 rounded-[20px] p-2 mb-8"
                >
                    <Tab
                        v-for="(tab, index) in tabs"
                        :key="index"
                        as="template"
                    >
                        <button
                            :class="
                                selectedIndex === index
                                    ? 'bg-white text-slate-900'
                                    : 'text-slate-600 hover:text-slate-900 border-gray-800 animate-pulse'
                            "
                            class="flex-1 text-sm font-medium h-8 px-4 rounded-2xl whitespace-nowrap focus-visible:outline-none ui-focus-visible:outline-none ui-focus-visible:ring ui-focus-visible:ring-indigo-300 transition-colors duration-150 ease-in-out"
                            @click="updateActiveTab(tab.title)"
                        >
                            {{ tab.title }}
                        </button>
                    </Tab>
                </TabList>
                <div
                    class="flex flex-col items-end justify-end w-full cursor-pointer"
                >
                    <img alt="BL Logo" class="w-20 h-20" src="/assets/b.svg" />
                </div>
            </div>

            <!-- Content -->
            <div class="w-full mx-auto">
                <div class="relative flex flex-col">
                    <slot :name="currentActiveTab" />
                </div>
            </div>
        </TabGroup>
    </div>
</template>
