<template>
    <div class="bg-black py-4">
        <div class="container px-12 flex items-center justify-between">
            <Logo />
            <div class="flex items-center gap-6">
                <NavList />
                <button @click="handleToggle" class="text-white">search</button>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { defineEmits } from 'vue';
    import Logo from './Logo.vue';
    import NavList from './NavList.vue';

    const emit = defineEmits(['toggleInput']);

    const handleToggle = () => {
        emit('toggleInput')
    }
</script>