<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />

    <div>
        <div class="container">
            <h1 class="mt-5 text-3xl font-medium">Movies</h1>

            <ul v-if="movies.length" class="flex gap-4 pb-4 pt-6">
                <MovieCard
                    v-for="movie in movies"
                    :key="movie.id"
                    :movie="movie"
                />
            </ul>
            <p v-else>Loading movies...</p>
        </div>
    </div>
</template>

<script setup>
import Header from './components/Header/Header.vue';
import GlobalSearch from './components/GlobalSearch.vue';
import HeroSection from './components/HeroSection/HeroSection.vue';
import MovieCard from './components/MovieCard.vue';
import { ref, onMounted } from 'vue';
import { movies as moviesData } from './assets/movies.js';

const movie = ref(null);
const movies = ref([]);
const isInputVisible = ref(false);

// const fetchMovies = async () => {
//     try {
//         const API_KEY = import.meta.env.VITE_TMBD_API_KEY;
//         const response = await fetch(
//             `https://api.themoviedb.org/3/movie/157336?api_key=${API_KEY}`,
//         );
//         const data = await response.json();

//         movie.value = data;
//     } catch (error) {
//         console.error(error);
//     }
// };

const toggleInput = () => {
    isInputVisible.value = !isInputVisible.value;
};

const setMovies = () => {
    setTimeout(() => {
        movies.value = moviesData;
    }, 1000);
};

onMounted(setMovies);
</script>
