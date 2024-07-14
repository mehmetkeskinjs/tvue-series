<template>
    <div class="relative w-1/6 rounded-lg shadow overflow-hidden">
        <span class="absolute right-4 top-2">{{ movie.rating }}</span>
        <img :src="movie.image" :alt="movie.title" class="w-full h-full object-cover">
        <div class="absolute inset-0 flex flex-col justify-end">
            <h3>{{ movie.title }}</h3>
            <span>{{ movie.date }}</span>
        </div>
    </div>
</template>

<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        movie: {
            type: Object,
            required: true
        }
    });
</script>