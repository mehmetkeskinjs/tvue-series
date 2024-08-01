<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />
    <MoviesSlider title="Movies" :isMoviesLoading="isMoviesLoading" :movies="movies"/>
    <TvShowsSlider title="Tv Shows" :isSeriesLoading="isSeriesLoading" :tvseries="tvseries" />
</template>

<script setup>
import { ref, onMounted } from 'vue';
import Header from './components/Header/Header.vue';
import GlobalSearch from './components/GlobalSearch.vue';
import HeroSection from './components/HeroSection/HeroSection.vue';
import MoviesSlider from './components/MoviesSlider/MoviesSlider.vue';
import TvShowsSlider from './components/TvShowsSlider/TvShowsSlider.vue';

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
