<template>
    <div v-if="isVisible">
        <!-- TODO: search icon will come here -->
        <input type="text" placeholder="Search for movie, tv show or people" class="w-full focus-within:outline-none px-8 py-2">
    </div>
</template>

<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        isVisible: Boolean
    })
</script>