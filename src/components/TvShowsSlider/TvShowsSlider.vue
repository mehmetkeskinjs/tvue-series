<template>
    <div class="bg-zinc-900 py-8">
        <div class="container px-12">
            <h1 class="text-3xl font-medium text-zinc-100">TV series</h1>

            <div v-if="isSeriesLoading" class="flex gap-2 pb-4 pt-6">
                <MovieCardSkeleton v-for="n in 6" :key="n" />
            </div>
            <ul
                v-else
                class="flex w-full min-w-full flex-row gap-2 overflow-auto pb-4 pt-6"
            >
                <MovieCard
                    v-for="show in tvseries"
                    :key="show.id"
                    :movie="show"
                />
            </ul>
        </div>
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
    isSeriesLoading: {
        type: Boolean,
        required: true
    },
    tvseries: {
        type: Array,
        required: true
    }
});
</script>