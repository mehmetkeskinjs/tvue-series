<template>
    <a href="#" class="relative w-1/6 overflow-hidden rounded-lg shadow-lg">
        <span
            class="absolute right-4 top-4 flex aspect-square w-8 items-center justify-center rounded-full bg-green-200 text-base font-semibold text-green-800 ring ring-green-600"
            >{{ movie.rating }}</span
        >
        <img
            :src="movie.image"
            :alt="movie.title"
            class="h-full w-full object-cover"
        />
        <div
            class="absolute inset-0 flex flex-col justify-end bg-gradient-to-t from-black p-4"
        >
            <h3 class="text-lg font-semibold text-white">{{ movie.title }}</h3>
            <span class="mt-1 text-xs text-gray-400">{{
                movie.date.split('-').reverse().join('.')
            }}</span>
        </div>
    </a>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
    movie: {
        type: Object,
        required: true,
    },
});
</script>
