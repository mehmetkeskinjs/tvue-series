<template>
    <a :href="link" class="text-white font-medium">
        {{ text }}
    </a>
</template>

<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        link: String,
        text: String,
        hasSublist: Boolean,
    });
</script>