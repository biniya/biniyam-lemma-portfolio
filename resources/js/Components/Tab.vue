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

// Create a ref to keep track of the active tab
const currentActiveTab = ref("home");

// Function to update the active tab
const updateActiveTab = (tabName) => {
    currentActiveTab.value = tabName.toLowerCase();
};

const { tabs, active } = toRefs(props);

watch(active, (newActive) => {
    emit("update:active", newActive);
});

watch(currentActiveTab, (newActive) => {
    emit("update:active", newActive);
});
</script>

<template>
    <div class="flex w-full flex-col items-center justify-center">
        <TabGroup v-slot="{ selectedIndex }">
            <!-- Buttons -->
            <div class="flex justify-center">
                <TabList
                    class="max-[480px]:max-w-[180px] inline-flex flex-wrap justify-center bg-slate-200 rounded-[20px] p-1 mb-8 min-[480px]:mb-12"
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
                                    : 'text-slate-600 hover:text-slate-900'
                            "
                            class="flex-1 text-sm font-medium h-8 px-4 rounded-2xl whitespace-nowrap focus-visible:outline-none ui-focus-visible:outline-none ui-focus-visible:ring ui-focus-visible:ring-indigo-300 transition-colors duration-150 ease-in-out"
                            @click="updateActiveTab(tab.title)"
                        >
                            {{ tab.title }}
                        </button>
                    </Tab>
                </TabList>
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
