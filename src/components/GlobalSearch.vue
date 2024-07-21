<template>
    <div v-if="isVisible">
        <!-- TODO: search icon will come here -->
        <input
            type="text"
            placeholder="Search for movie, tv show or people"
            class="fixed top-16 z-10 w-full px-8 py-2 transition-all focus-within:outline-none"
        />
    </div>
</template>

<script setup>
const props = defineProps({
    isVisible: Boolean,
});
</script>
