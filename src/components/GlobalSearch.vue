<template>
    <div v-if="isActive">
        <!-- TODO: search icon will come here -->
        <input type="text" placeholder="Search for movie, tv show or people" class="w-full focus-within:outline-none px-8 py-2">
    </div>
</template>

<script setup>
    const props = defineProps({
        isActive: Boolean
    })
</script>