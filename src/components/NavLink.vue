<template>
    <a :href="link" class="text-white font-medium">
        {{ text }}
    </a>
</template>

<script setup>
    const props = defineProps({
        link: String,
        text: String,
        hasSublist: Boolean,
    });
</script>