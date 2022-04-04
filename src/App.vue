<script setup>
import LogoRcgt from "./components/icons/LogoRcgt.vue";
import IconPhone from "./components/icons/IconPhone.vue";
import IconMail from "./components/icons/IconMail.vue";
import { ref } from "vue";
import TheButtonMenu from "./components/TheButtonMenu.vue";
import TheMain from "./components/TheMain.vue";
import TheMenu from "./components/TheMenu.vue";
import TheFooter from "./components/TheFooter.vue";
import TheNavHeader from "./components/TheNavHeader.vue";

const activeMenu = ref(false);

function toggleMenu(e) {
    activeMenu.value = e;
    if (activeMenu.value) {
        document.body.style.overflow = "hidden";
        document.getElementById("nav-mobile").style.overflowY = "scroll";
    } else {
        document.getElementById("nav-mobile").style.overflowY = "hidden";
        document.body.style.overflow = "auto";
    }
}

</script>

<template>
    <div class="container">
        <header class="header">
            <a v-if="!activeMenu" class="header__logo" href="/" aria-label="Link to home page">
                <LogoRcgt />
            </a>
            <div v-else class="header__contact slide-contact">
                <a href="tel:1-866-692-1192" class="header__contact-btn" aria-label="Telephone">
                    <IconPhone />
                </a>
                <a
                    href="/"
                    class="header__contact-btn header__contact-btn--fill"
                    aria-label="Link to Contact page"
                >
                    <IconMail />
                </a>
            </div>
            <div class="header__menu">
                <a :class="[activeMenu ? 'header__language' : 'hidden']" href="/">en</a>
                <TheButtonMenu @toggle-menu="toggleMenu" />
            </div>
            <div class="header__nav">
                <TheNavHeader />
            </div>
        </header>
        <nav class="nav__mobile" id="nav-mobile" :class="{ 'nav__mobile--shrink': !activeMenu }">
            <TheMenu :active-menu="activeMenu" />
        </nav>

        <main class="main">
            <TheMain />
        </main>
        <footer class="footer">
            <TheFooter />
        </footer>
    </div>
</template>

<style>
@import "./assets/base.css";

.hidden {
    display: none;
}

.container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows:
        var(--height-header) min-content minmax(min-content, 1fr)
        min-content;
    grid-template-areas:
        "header"
        "nav"
        "main"
        "footer";
    height: 100%;
    justify-items: center;
}

.header {
    display: flex;
    grid-area: header;
    width: 100%;
    padding: 16px 16px 8px 16px;
    background-color: var(--color-background-white);
    justify-content: space-between;
    align-items: center;
}

.header__logo {
    display: block;
}

.header__contact {
    display: inline-flex;
    gap: 10px;
}

.slide-contact {
    animation: slide-contact 0.5s cubic-bezier(0.645, 0.045, 0.355, 1);
}

@keyframes slide-contact {
    0% {
        transform: translateX(80vw);
    }
    100% {
        transform: translateX(0);
    }
}

.header__contact-btn {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    border-radius: var(--border-radius);
    width: 55px;
    height: 55px;
    border: 1px solid var(--color-border);
    transition: width 0.3s,
        background-color 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.header__contact-btn:hover {
    background-color: var(--color-background-dark);
    color: var(--color-text-white);
}

.header__contact-btn:hover svg {
    stroke: var(--color-white);
    transition: stroke 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.header__contact-btn--fill:hover svg {
    fill: var(--color-white);
    transition: fill 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.header__menu {
    display: inline-flex;
    gap: 10px;
    align-items: center;
}

.header__language {
    text-decoration: none;
    text-transform: uppercase;
    color: var(--text-color-secondary-dark);
    font-weight: 500;
}

.header__nav {
    display: none;
}

.nav__mobile {
    grid-area: nav;
    position: absolute;
    z-index: 3;
    width: 100%;
    height: 100vh;
    max-height: calc(100vh - var(--height-header));
    overflow-y: scroll;
    padding-bottom: 80px;
    background-color: var(--color-white);
    transform-origin: 0 0;
    transition: transform 0.5s;
}

.nav__mobile--shrink {
    transform-origin: 0 0;
    transform: scale(1, 0);
    transition: transform 0.5s 0.5s;
}

.main {
    grid-area: main;
    max-width: 1440px;
    width: 100%;
}

.footer {
    grid-area: footer;
    width: 100%;
}
@media (min-width: 481px) {
    .header__contact-btn {
        width: 180px;
    }
}

@media (min-width: 1081px) {
    .header__menu {
        display: none;
    }

    .header__nav {
        display: initial;
    }
}
</style>
