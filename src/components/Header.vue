<template>
    <div class="bg-black py-4">
        <div class="container px-12 flex items-center justify-between">
            <Logo />
            <div class="flex items-center gap-6">
                <NavList />
                <HeaderSearchIcon />
            </div>
        </div>
    </div>
</template>

<script setup>
    import HeaderSearchIcon from './HeaderSearchIcon.vue';
    import Logo from './Logo.vue';
    import NavList from './NavList.vue';

</script>