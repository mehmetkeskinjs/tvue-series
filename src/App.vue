<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />

    <!-- TODO: Componentize this -->
    <div class="container px-12 py-8">
        <h1 class="text-3xl font-medium">Movies</h1>

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
import Header from './components/Header/Header.vue';
import GlobalSearch from './components/GlobalSearch.vue';
import HeroSection from './components/HeroSection/HeroSection.vue';
import MovieCard from './components/MovieCard.vue';
import { ref, onMounted } from 'vue';
import MovieCardSkeleton from './components/MovieCardSkeleton.vue';

const movies = ref([]);
const tvseries = ref([]);
const isInputVisible = ref(false);
const isMoviesLoading = ref(true);
const isSeriesLoading = ref(true);

const options = {
    method: 'GET',
    headers: {
        accept: 'application/json',
        Authorization: `Bearer ${import.meta.env.VITE_READ_ACCESS_TOKEN}`,
    },
};

const fetchMovies = async () => {
    try {
        const response = await fetch(
            'https://api.themoviedb.org/3/trending/movie/week?language=en-US',
            options,
        );
        const { results } = await response.json();
        movies.value = results;
    } catch (error) {
        console.error(error);
    } finally {
        isMoviesLoading.value = false;
    }
};

const fetchTVSeries = async () => {
    try {
        const response = await fetch(
            'https://api.themoviedb.org/3/tv/airing_today?language=en-US&page=1',
            options,
        );
        const { results } = await response.json();
        tvseries.value = results;
    } catch (error) {
        console.error(error);
    } finally {
        isSeriesLoading.value = false;
    }
};

const toggleInput = () => {
    isInputVisible.value = !isInputVisible.value;
};

onMounted(() => {
    fetchMovies();
    fetchTVSeries();
});
</script>
