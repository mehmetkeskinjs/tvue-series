<template>
    <div class="relative h-[400px]">
        <img
            src="https://pbs.twimg.com/media/FaU8M6iUUAAG8aV?format=jpg&name=large"
            class="h-full w-full scale-x-[-1] object-cover"
            alt=""
        />
        <div class="absolute inset-0 flex items-center bg-black bg-opacity-40">
            <div class="container flex flex-col justify-center gap-3 px-12">
                <h1 class="mt-4 text-5xl font-bold text-white">Welcome.</h1>
                <p class="text-xl text-zinc-100/90">
                    Millions of movies, TV shows and people to discover. Explore
                    now.
                </p>

                <SearchInput />
            </div>
        </div>
    </div>
</template>

<script setup>
import SearchInput from './SearchInput.vue';
</script>
