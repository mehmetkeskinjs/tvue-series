<template>
    <div v-if="isVisible" class="relative">
        <div class="absolute left-10 top-[4.5rem] z-20 text-zinc-800/40">
            <svg
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="size-6"
            >
                <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
                />
            </svg>
        </div>
        <input
            type="text"
            placeholder="Search for movie, tv show or people"
            class="fixed top-16 z-10 w-full bg-zinc-50 py-2 pl-20 pr-8 outline-none transition-all focus-within:outline-none"
        />
    </div>
</template>

<script setup>
const props = defineProps({
    isVisible: Boolean,
});
</script>
