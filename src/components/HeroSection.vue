<template>
    <div class="relative h-[400px]">
        <img src="https://pbs.twimg.com/media/FaU8M6iUUAAG8aV?format=jpg&name=large" class="w-full h-full object-cover scale-x-[-1]" alt="">
        <div class="absolute inset-0 bg-black bg-opacity-40 flex items-center">
            <div class="container px-12 flex flex-col justify-center gap-3">
                <h1 class="text-white font-bold text-5xl mt-4">Welcome.</h1>
                <p class="text-zinc-100/90 text-xl">Millions of movies, TV shows and people to discover. Explore now.</p>
                
                <SearchInput />
            </div>
        </div>
    </div>
</template>

<script setup>
    import SearchInput from './SearchInput.vue';


</script>