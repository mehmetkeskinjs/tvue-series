<template>
    <div class="relativepx-12 container py-8">
        <div class="flex items-center justify-between">
            <div class="flex items-center gap-4">
                <h1 class="text-3xl font-medium">{{ title }}</h1>
                <div class="rounded-full border border-black p-4">
                    Nagivator
                </div>
            </div>
            <div class="flex items-center gap-3">
                <button
                    class="flex aspect-square w-10 cursor-pointer items-center justify-center rounded-full bg-neutral-200 ring ring-neutral-300/20"
                >
                    <svg
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke-width="1.5"
                        stroke="currentColor"
                        class="mr-[2px] size-5"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="M15.75 19.5 8.25 12l7.5-7.5"
                        />
                    </svg>
                </button>
                <button
                    class="flex aspect-square w-10 cursor-pointer items-center justify-center rounded-full bg-neutral-200 ring ring-neutral-300/20"
                >
                    <svg
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke-width="1.5"
                        stroke="currentColor"
                        class="ml-[2px] size-5"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            d="m8.25 4.5 7.5 7.5-7.5 7.5"
                        />
                    </svg>
                </button>
            </div>
        </div>

        <div v-if="isMoviesLoading" class="flex gap-2 pb-4 pt-6">
            <MovieCardSkeleton v-for="n in 6" :key="n" />
        </div>
        <ul
            v-else
            class="no-scrollbar flex w-full min-w-full snap-x snap-mandatory flex-row gap-2 overflow-auto pb-4 pt-6"
        >
            <!-- <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie" /> -->
            <NewMovieCard
                v-for="movie in movies"
                :key="movie.id"
                :movie="movie"
            />
        </ul>
    </div>
</template>

<script setup>
import MovieCardSkeleton from '../MovieCardSkeleton.vue';
import MovieCard from '../MovieCard.vue';
import NewMovieCard from '../NewMovieCard.vue';

defineProps({
    title: {
        type: String,
        required: true,
    },
    isMoviesLoading: {
        type: Boolean,
        required: true,
    },
    movies: {
        type: Array,
        required: true,
    },
});
</script>
