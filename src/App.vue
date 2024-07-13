<template>
    <Header :isVisible="isInputVisible" @toggleInput="toggleInput" />
    <GlobalSearch :isVisible="isInputVisible" />
    <HeroSection />
    <div class="p-8">
        <h1>Movies</h1>
        <ul v-if="movies.length" class="flex flex-wrap gap-4">
          <li v-for="movie in movies" :key="movie.id" class="border max-w-[150px]">
            <img :src="movie.image" alt="Movie Image" />
            <h2>{{ movie.title }}</h2>
            <p>Rating: {{ movie.rating }}</p>
            <p>Release Date: {{ movie.date }}</p>
          </li>
        </ul>
        <p v-else>Loading movies...</p>
      </div>
</template>

<script setup>
    import Header from './components/Header.vue';
    import GlobalSearch from './components/GlobalSearch.vue';
    import HeroSection from './components/HeroSection.vue';
    import { ref, onMounted } from 'vue';
    import { movies as moviesData } from './assets/movies.js'

    const movie = ref(null);
    const movies = ref([]);
    const isInputVisible = ref(false);

    // const fetchMovies = async () => {
    //     try {
    //         const API_KEY = import.meta.env.VITE_TMBD_API_KEY;
    //         const response = await fetch(`https://api.themoviedb.org/3/movie/157336?api_key=${ API_KEY }`);
    //         const data = await response.json();
            
    //         movie.value = data;
    //     } catch (error) {
    //         console.error(error);
    //     }
    // }

    const toggleInput = () => {
        isInputVisible.value = !isInputVisible.value;
    };

    const setMovies = () => {
        setTimeout(() => {
            movies.value = moviesData;
        }, 1000);
        console.log(movies)
    }

    onMounted(setMovies);
</script>