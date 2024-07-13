<template>
    <Header />
    <HeroSection />
</template>

<script setup>
    import Header from './components/Header.vue';
    import HeroSection from './components/HeroSection.vue';
    import { ref, onMounted } from 'vue';

    const movie = ref(null);

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

    onMounted(fetchMovies);
</script>