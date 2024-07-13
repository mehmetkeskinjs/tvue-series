<template>
    <div class="flex gap-6 items-center justify-center">
        <NavLink
            v-for="link in navLinks"
            :text="link.linkText"
            :link="link.linkUrl"
        />
    </div>
</template>

<script setup>
    import NavLink from './NavLink.vue';

    const navLinks = [
        {
            linkText: 'Movies',
            linkUrl: '#',
            hasSublist: true,
            sublist: [
                {
                    'Popular': '#',
                    'Now Playing': '#'
                }
            ]
        },
        {
            linkText: 'Tv Shows',
            linkUrl: '#',
            hasSublist: false,
        }
    ]
</script>