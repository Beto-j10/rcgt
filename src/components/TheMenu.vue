<script setup>
import IconNavigation from "./icons/IconNavigation.vue";
import IconClient from "./icons/IconClient.vue";
import IconArrow from "./icons/iconArrow.vue";
import VBarSocial from "./VBarSocial.vue";

defineProps({
    activeMenu: {
        default: false,
        type: Boolean,
    },
})

const itemsNavBottom1 = [
    {
        title: "Notre offre",
        link: "/",
    },
    {
        title: "Nos experts",
        link: "/",
    },
    {
        title: "Nos conseils",
        link: "/",
    },
    {
        title: "Actualités",
        link: "/",
    },
];
const itemsNavBottom2 = [
    {
        title: "Dossier | Impôts",
        link: "/",
    },
    {
        title: "Infolettre",
        link: "/",
    },
    {
        title: "Carrières",
        link: "/",
    },
];

</script>

<template>
    <div class="division" :class="[activeMenu ? 'opacity-enter-1' : 'opacity-leave-2']"></div>
    <ul class="nav__bottom" :class="[activeMenu ? 'opacity-enter-1' : 'opacity-leave-1']">
        <li v-for="item in itemsNavBottom1" :key="item.title" class="nav__item">
            <a :href="item.link" class="nav__link">{{ item.title }}</a>
        </li>
    </ul>
    <ul
        class="nav__bottom nav__bottom--padding"
        :class="[activeMenu ? 'opacity-enter-2' : 'opacity-leave-2']"
    >
        <li
            v-for="item in itemsNavBottom2"
            :key="item.title"
            class="nav__item nav__item--no-border"
        >
            <a :href="item.link" class="nav__link">{{ item.title }}</a>
        </li>
        <li class="nav__item nav__item--no-border">
            <a class="nav__link" href="/" target>
                <IconNavigation />Nos bureaux
            </a>
        </li>
        <li class="nav__item nav__item--no-border">
            <a class="nav__link" href="/" target="_blank">
                <IconClient />espaceClient
            </a>
        </li>
    </ul>
    <button
        class="nav__about-button"
        aria-label="Menu about"
        :class="[activeMenu ? 'opacity-enter-2' : 'opacity-leave-2']"
    >
        À propos
        <IconArrow />
    </button>
    <div class="division" :class="[activeMenu ? 'opacity-enter-2' : 'opacity-leave-2']"></div>
    <VBarSocial :class="[activeMenu ? 'opacity-enter-2' : 'opacity-leave-2']" />
</template>

<style scoped>

.nav__bottom {
    display: flex;
    flex-direction: column;
    list-style: none;
    padding: 0;
}

.nav__bottom--padding {
    padding: 16px 0;
    border-bottom: 2px solid var(--color-border-light);
}

.opacity-enter-1 {
    transition: opacity 0.5s 0.3s;
}
.opacity-leave-1 {
    opacity: 0;
    transition: opacity 0.5s 0.3s;
}

.opacity-enter-2 {
    transition: opacity 0.5s 0.6s;
}
.opacity-leave-2 {
    opacity: 0;
    transition: opacity 0.5s;
}

.nav__item {
    padding: 4px 32px;
    border-bottom: 2px solid var(--color-border-light);
}

.nav__item--no-border {
    border-bottom: none;
}

.nav__link {
    display: block;
    color: var(--text-color-mute);
    text-decoration: none;
    font-size: var(--font-size-x-large);
    line-height: 1.4;
    font-weight: 500;
    padding: 10px 0;
}

.nav__about-button {
    border: none;
    background-color: transparent;
    padding: 16px 48px 16px 32px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    cursor: pointer;
    color: var(--text-color-soft);
    font-size: var(--font-size-medium);
    font-weight: 500;
}

.division {
    width: 100%;
    height: 4px;
    background-color: var(--color-border-light);
}
</style>