<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />

    <!-- TODO: Componentize this -->
    <div class="container px-12">
        <h1 class="mt-5 text-3xl font-medium">Movies</h1>

        <ul
            v-if="movies.length"
            class="flex w-full min-w-full flex-row gap-2 overflow-scroll pb-4 pt-6"
        >
            <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie" />
        </ul>
        <p v-else>Loading movies...</p>
    </div>
</template>

<script setup>
import Header from './components/Header/Header.vue';
import GlobalSearch from './components/GlobalSearch.vue';
import HeroSection from './components/HeroSection/HeroSection.vue';
import MovieCard from './components/MovieCard.vue';
import { ref, onMounted } from 'vue';

const movies = ref([]);
const isInputVisible = ref(false);

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
        console.log(results);
        movies.value = results;
    } catch (error) {
        console.error(error);
    }
};

const toggleInput = () => {
    isInputVisible.value = !isInputVisible.value;
};

onMounted(fetchMovies);
</script>
