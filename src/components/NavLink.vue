<template>
    <a :href="link" class="font-medium text-white">
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
