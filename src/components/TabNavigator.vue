<template>
    <div class="rounded-md bg-neutral-300/50 p-1">
        <button
            v-for="tab in tabs"
            :key="tab.id"
            :class="{
                'bg-white': activeIndex === tab.id - 1,
            }"
            @click="setActiveIndex(tab.id)"
            class="rounded px-4 py-1 capitalize transition-all duration-200"
        >
            {{ tab.name }}
        </button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

const activeIndex = ref(0);
const tabs = [
    {
        id: 1,
        name: 'popular',
    },
    {
        id: 2,
        name: 'top rated',
    },
];

const setActiveIndex = (id) => {
    activeIndex.value = id - 1;
};
</script>
