<template>
    <a
        href="#"
        class="min-w-[250px] snap-start overflow-hidden rounded-3xl bg-white text-neutral-500 shadow-lg transition duration-200 hover:bg-neutral-200/50"
    >
        <h3 class="truncate p-4">
            {{ movie.title || movie.name }}
        </h3>

        <div class="h-full max-h-64 p-4 2xl:max-h-80">
            <img
                :src="generateImage(movie.poster_path)"
                :alt="movie.title"
                class="mx-auto block h-full rounded-2xl shadow-2xl"
            />
        </div>
        <div class="flex items-center justify-between gap-4 p-4">
            <span class="mt-1 text-xs">{{ date }}</span>

            <span
                class="mt-2 flex w-fit items-center rounded-lg px-2 py-1 text-base font-medium text-neutral-500 ring-1 ring-inset ring-neutral-700"
            >
                {{ movie.vote_average.toFixed(1) }}
                <span class="-ml-1 flex items-center font-light">
                    <svg viewBox="0 0 10 16" fill="currentColor" class="size-4">
                        <path
                            fill-rule="evenodd"
                            d="M10.074 2.047a.75.75 0 0 1 .449.961L6.705 13.507a.75.75 0 0 1-1.41-.513L9.113 2.496a.75.75 0 0 1 .961-.449Z"
                            clip-rule="evenodd"
                        /></svg
                    >10</span
                >
            </span>
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

const generateImage = (path) => {
    return `https://media.themoviedb.org/t/p/w440_and_h660_face/${path}`;
};

const createNewDate = (rawDate) => {
    if (rawDate === '') {
        date.value = '';

        return;
    }

    const splittedDate = rawDate.split('-');

    date.value = `${months[Number(splittedDate[1]) - 1].slice(0, 3)} ${splittedDate[2]}, ${splittedDate[0]}`;
};

onMounted(() => {
    if (props.movie.release_date) {
        createNewDate(props.movie.release_date);
    } else {
        createNewDate(props.movie.first_air_date);
    }
});
</script>
