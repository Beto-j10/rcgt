<script setup>
import { onUnmounted, ref } from 'vue';


const emmit = defineEmits([
    'toggleMenu',
]);
const activeMenu = ref(false);
const mediaQuery = window.matchMedia('(min-width: 1081px)')

function handleMediaQueryChange(e) {
    if (e.matches) {
        activeMenu.value = false;
        emmit('toggleMenu', false);
    }
}
mediaQuery.addEventListener('change', handleMediaQueryChange)

onUnmounted(() => {
    mediaQuery.removeEventListener('change', handleMediaQueryChange)
})

</script>

<template>
    <button
        @click="$emit('toggleMenu', activeMenu = !activeMenu)"
        class="header__menu-button"
        :class="{ 'header__menu-button--open': activeMenu }"
        aria-label="Toggle mobile menu"
    >
        <span class="header__menu-button-line" :class="{ 'line1': activeMenu }"></span>
        <span class="header__menu-button-line" :class="{ 'line2': activeMenu }"></span>
        <span class="header__menu-button-line" :class="{ 'line3': activeMenu }"></span>
    </button>
</template>

<style scoped>
.header__menu-button {
    margin: 0;
    padding: 0;
    border: none;
    width: 30px;
    height: 28px;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    background-color: var(--color-background-white);
    transition: transform 0.5s;
}

.header__menu-button--open {
    transform: matrix(0, -1, 1, 0, 0, 0);
}

.line1 {
    transform: matrix(0.71, -0.71, 0.71, 0.71, 0, 9);
}

.line2 {
    visibility: hidden;
    opacity: 0;
}

.line3 {
    transform: matrix(0.71, 0.71, -0.71, 0.71, 0, -10);
}

.header__menu-button-line {
    display: block;
    width: 30px;
    height: 3px;
    background-color: var(--text-color-secondary-dark);
    transition: transform 0.5s;
}
</style>