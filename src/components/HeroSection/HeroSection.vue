<template>
    <div class="relative h-screen">
        <img
            :src="heroMovieDetail.image"
            class="h-full w-full object-cover"
            alt=""
        />
        <div
            class="absolute inset-0 flex h-full items-end bg-gradient-to-t from-black/80 to-black/50 2xl:pb-24"
        >
            <div
                class="container flex w-fit flex-col items-center justify-between px-12"
            >
                <h1 class="mt-5 text-5xl font-normal text-zinc-100">
                    Find movies & TV shows
                </h1>
                <p class="mt-3 text-lg font-light tracking-wide text-zinc-300">
                    Discover your favorite movies or TV shows
                </p>

                <SearchInput />
                <HeroMovie :movie="heroMovieDetail" />
                <PlatformList :platforms="platformList" />
            </div>
        </div>
    </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import HeroMovie from './HeroMovie.vue';
import PlatformList from './PlatformList.vue';
import SearchInput from './SearchInput.vue';
import { platforms as platformData } from '../../assets/platforms.js';

const heroMovieDetail = ref({});
const platformList = ref([]);

onMounted(() => {
    heroMovieDetail.value = {
        name: 'Joker',
        year: '2019',
        link: '#',
        image: 'https://images.alphacoders.com/104/1042134.jpg',
    };
});

onMounted(() => {
    platformList.value = platformData;
});
</script>
