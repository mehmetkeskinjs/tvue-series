<template>
    <div class="container relative px-12 py-8">
        <div class="flex items-center justify-between">
            <div class="flex items-end gap-6">
                <h1 class="text-3xl font-medium">{{ title }}</h1>

                <TabNavigator />
            </div>
            <div class="flex items-center gap-3">
                <button
                    :class="{
                        'cursor-pointer bg-neutral-200 ring-neutral-300/20':
                            currentIndex !== 0,
                        'cursor-not-allowed bg-neutral-200/40 text-neutral-400 ring-neutral-100/20':
                            currentIndex === 0,
                    }"
                    @click="currentIndex--"
                    :disabled="currentIndex === 0"
                    class="flex aspect-square w-10 cursor-pointer items-center justify-center rounded-full ring"
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
                    :class="{
                        'cursor-pointer bg-neutral-200 ring-neutral-300/20':
                            currentIndex !== sliderLength,
                        'cursor-not-allowed bg-neutral-200/40 text-neutral-400 ring-neutral-100/20':
                            currentIndex === sliderLength,
                    }"
                    :disabled="currentIndex === sliderLength"
                    @click="currentIndex++"
                    class="flex aspect-square w-10 cursor-pointer items-center justify-center rounded-full ring"
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
import NewMovieCard from '../NewMovieCard.vue';
import TabNavigator from '../TabNavigator.vue';
import { ref } from 'vue';

const currentIndex = ref(0);
const sliderLength = ref(10);

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
