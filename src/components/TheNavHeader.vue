<script setup>
import IconClient from './icons/IconClient.vue';

const itemsNav = [
    {
        title: "Dossier | Impôts",
        link: "/",
        class: "nav__link nav__link--border"
    },
    {
        title: "Infolettre",
        link: "/",
    },
    {
        title: "Carrières",
        link: "/",
    },
    {
        title: "Nos bureaux",
        link: "/",
    },
]

</script>

<template>
        <ul class="nav__list">
            <li v-for="item in itemsNav" :key="item.title" class="nav__item">
                <a :href="item.link" :class="[item?.class ? item.class : 'nav__link']">{{ item.title }}</a>
            </li>
            <li class="nav__item nav__item--border">
                <a href="/" class="nav__link nav__link--icon">
                    <IconClient />
                    espaceClient
                </a>
            </li>
            <li class="nav__item nav__item--border">
                <a href="/" class="nav__link" aria-label="English version">
                    EN
                </a>
            </li>
        </ul>
</template>

<style>

    .nav__list {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 15px;
        margin: 0;
        list-style: none;
    }

    .nav__item {
        padding-left: 15px;
        margin-left: 15px;
    }

    .nav__item--border {
        border-left: 1px solid #4f2d7f33;
    }

    .nav__link {
        text-decoration: none;
        font-size: var(--font-size-base);
        font-weight: 500;
        color: var(--text-color-mute);
        transition: color .35s ease;
    }

    .nav__link:hover {
        color: var(--text-color-secondary-dark);
    }

    .nav__link svg {
        transition: stroke .35s ease, fill .35s ease;
        margin-right: 8px;
    }

    .nav__link:hover svg {
        stroke: var(--text-color-secondary-dark);
        fill: var(--text-color-secondary-dark);
    }

    .nav__link--border {
        padding: 10px 20px;
        border: 1px solid var(--color-border);
        border-radius: 25px;
    }
</style>