<template>
    <a href="#" class="relative w-1/6 overflow-hidden rounded-lg shadow-lg">
        <span
            class="absolute right-4 top-4 flex aspect-square w-8 items-center justify-center rounded-full bg-green-200 text-base font-semibold text-green-800 ring ring-green-600"
            >{{ movie.rating }}</span
        >
        <img
            :src="movie.image"
            :alt="movie.title"
            class="h-full w-full object-cover"
        />
        <div
            class="absolute inset-0 flex flex-col justify-end bg-gradient-to-t from-black p-4"
        >
            <h3 class="truncate text-base font-semibold text-white">
                {{ movie.title }}
            </h3>
            <span class="mt-1 text-xs text-gray-400">{{ date }}</span>
        </div>
    </a>
</template>

<script setup>
import { onMounted, ref } from 'vue';

const date = ref('');
const months = [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
    'July',
    'August',
    'September',
    'October',
    'November',
    'December',
];

const props = defineProps({
    movie: {
        type: Object,
        required: true,
    },
});

const createNewDate = (rawDate) => {
    const splittedDate = rawDate.split('-');

    date.value = `${months[Number(splittedDate[1])].slice(0, 3)} ${splittedDate[2]}, ${splittedDate[0]}`;
};

onMounted(() => {
    createNewDate(props.movie.date);
});
</script>
