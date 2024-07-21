<template>
    <div
        class="absolute top-0 z-10 flex h-16 w-screen items-center bg-transparent"
    >
        <div class="container flex items-center justify-between px-12">
            <Logo />
            <div class="flex items-center gap-6">
                <NavList />
                <button @click="handleToggle" class="font-bold text-white">
                    <span v-if="isVisible">
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke-width="2"
                            stroke="currentColor"
                            class="size-6"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                d="M6 18 18 6M6 6l12 12"
                            />
                        </svg>
                    </span>
                    <span v-else>
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke-width="2"
                            stroke="currentColor"
                            class="size-6"
                        >
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
                            />
                        </svg>
                    </span>
                </button>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineEmits } from 'vue';
import Logo from './Logo.vue';
import NavList from './NavList.vue';

const props = defineProps({
    isVisible: Boolean,
});

const emit = defineEmits(['toggleInput']);

const handleToggle = () => {
    emit('toggleInput');
};
</script>
