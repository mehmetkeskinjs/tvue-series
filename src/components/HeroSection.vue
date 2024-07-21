<template>
    <div class="relative h-screen">
        <img
            src="https://images.alphacoders.com/104/1042134.jpg"
            class="h-full w-full object-cover"
            alt=""
        />
        <div
            class="absolute inset-0 flex h-full items-end bg-gradient-to-t from-black/80 to-black/50 2xl:pb-24"
        >
            <div
                class="container flex w-fit flex-col items-center justify-between px-12"
            >
                <h1 class="mt-5 text-5xl font-normal text-zinc-100">
                    Find movies & TV shows
                </h1>
                <p class="mt-3 text-lg font-light tracking-wide text-zinc-300">
                    Discover your favorite movies or TV shows
                </p>

                <SearchInput />

                <div class="mt-10 flex w-full items-center justify-between">
                    <div class="flex flex-col text-xl">
                        <span class="text-zinc-200">Joker</span>
                        <span class="text-xs font-light text-zinc-400"
                            >2019</span
                        >
                    </div>
                    <button
                        class="group flex items-center rounded-full bg-white px-3 py-1"
                    >
                        See details
                        <span
                            class="mt-[2px] transition-all duration-300 group-hover:translate-x-1"
                        >
                            <svg
                                viewBox="0 0 16 16"
                                fill="currentColor"
                                class="size-4"
                            >
                                <path
                                    fill-rule="evenodd"
                                    d="M6.22 4.22a.75.75 0 0 1 1.06 0l3.25 3.25a.75.75 0 0 1 0 1.06l-3.25 3.25a.75.75 0 0 1-1.06-1.06L8.94 8 6.22 5.28a.75.75 0 0 1 0-1.06Z"
                                    clip-rule="evenodd"
                                />
                            </svg>
                        </span>
                    </button>
                </div>

                <div
                    class="mt-6 flex w-full items-center justify-between gap-2 pb-10"
                >
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://sm.ign.com/ign_tr/cover/p/prime-vide/prime-video_mxh1.jpg"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >Prime Video</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://images.ctfassets.net/y2ske730sjqp/5QQ9SVIdc1tmkqrtFnG9U1/de758bba0f65dcc1c6bc1f31f161003d/BrandAssets_Logos_02-NSymbol.jpg?w=940"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >Netflix</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://sm.ign.com/ign_tr/cover/p/paramount-/paramount-plus_w4bm.jpg"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >Paramount+</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://i.pinimg.com/736x/8b/02/00/8b020050690f955ccb306cdf51324aea.jpg"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >HBOMAX</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://www.apple.com/newsroom/images/tile-images/Apple-introduces-apple-tv-plus-03252019.jpg.news_app_ed.jpg"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >Apple TV</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                    <div class="flex w-[1/6] flex-col items-center">
                        <img
                            src="https://asset.brandfetch.io/id4KRloCCr/id70LTaZPD.jpeg"
                            class="aspect-square w-14 rounded-lg bg-white object-cover"
                            alt=""
                        />
                        <span class="mt-2 text-xs font-light text-slate-300"
                            >Hulu</span
                        >
                        <span
                            class="text text-[11px] font-light text-slate-300/60"
                            >Country</span
                        >
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import SearchInput from './SearchInput.vue';
</script>
