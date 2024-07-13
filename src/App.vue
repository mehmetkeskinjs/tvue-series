<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />
</template>

<script setup>
    import Header from './components/Header.vue';
    import GlobalSearch from './components/GlobalSearch.vue';
    import HeroSection from './components/HeroSection.vue';
    import { ref, onMounted } from 'vue';

    const movie = ref(null);
    const isInputVisible = ref(false);

    const fetchMovies = async () => {
        try {
            const API_KEY = import.meta.env.VITE_TMBD_API_KEY;
            const response = await fetch(`https://api.themoviedb.org/3/movie/157336?api_key=${ API_KEY }`);
            const data = await response.json();
            
            movie.value = data;
        } catch (error) {
            console.error(error);
        }
    }

    const toggleInput = () => {
        isInputVisible.value = !isInputVisible.value;
    };

    onMounted(fetchMovies);
</script>