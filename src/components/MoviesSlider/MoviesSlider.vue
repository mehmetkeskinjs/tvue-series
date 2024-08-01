<template>
    <div class="container px-12 py-8">
        <h1 class="text-3xl font-medium">{{ title }}</h1>

        <div v-if="isMoviesLoading" class="flex gap-2 pb-4 pt-6">
            <MovieCardSkeleton v-for="n in 6" :key="n" />
        </div>
        <ul
            v-else
            class="flex w-full min-w-full flex-row gap-2 overflow-auto pb-4 pt-6"
        >
            <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie" />
        </ul>
    </div>
</template>

<script setup>
import MovieCardSkeleton from "../MovieCardSkeleton.vue"
import MovieCard from "../MovieCard.vue";

defineProps({
    title: {
        type: String,
        required: true
    }, 
    isMoviesLoading: {
        type: Boolean,
        required: true
    },
    movies: {
        type: Array,
        required: true
    }
});
</script>