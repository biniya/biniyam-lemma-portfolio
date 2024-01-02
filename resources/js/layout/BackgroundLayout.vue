<script setup></script>
<template>
    <div class="relative">
        <div class="absolute inset-0 mx-auto w-full z-0 flex bg-white p-16">
            <div
                class="relative w-full flex flex-wrap justify-center items-center"
            >
                <div
                    class="w-full gradient-mask scale-75 grid-rows-7 lg:grid-rows-12 z-0 grid grid-cols-7 border bg-blue-100 opacity-[0.4] lg:grid-cols-12 lg:bg-transparent"
                >
                    <div
                        v-for="index in 70"
                        :key="index"
                        :class="index % 5 ? '' : 'bg-blue-300 '"
                        class="aspect-square border border-blue-200"
                    />
                </div>
            </div>
        </div>
        <slot></slot>
    </div>
</template>

<style scoped>
.gradient-mask {
    mask-image: radial-gradient(rgba(0, 0, 0, 0.7) 0%, transparent 100%);
}
</style>
