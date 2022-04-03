<script setup>
import IconLinkedin from "./icons/iconLinkedin.vue";
import IconFacebook from "./icons/iconFacebook.vue";
import IconTwitter from "./icons/iconTwitter.vue";
import IconInstagram from "./icons/iconInstagram.vue";
import IconYoutube from "./icons/iconYoutube.vue";
</script>
<template>
    <ul class="nav__social">
        <li>
            <a
                class="nav__social-link"
                href="https://www.linkedin.com/company/16672/"
                target="_blank"
                aria-label="Link to RCGT Linkedin page"
            >
                <IconLinkedin />
            </a>
        </li>
        <li>
            <a
                class="nav__social-link"
                href="https://www.facebook.com/RCGTweb"
                target="_blank"
                aria-label="Link to RCGT Facebook page"
            >
                <IconFacebook />
            </a>
        </li>
        <li>
            <a
                class="nav__social-link"
                href="https://twitter.com/RCGT"
                target="_blank"
                aria-label="Link to RCGT Twitter page"
            >
                <IconTwitter />
            </a>
        </li>
        <li>
            <a
                class="nav__social-link"
                href="https://www.instagram.com/rcgt_com/"
                target="_blank"
                aria-label="Link to RCGT instagram page"
            >
                <IconInstagram />
            </a>
        </li>
        <li class="nav__social-item">
            <a
                class="nav__social-link"
                href="https://www.youtube.com/user/RCGTweb"
                target="_blank"
                aria-label="Link to RCGT youtube page"
            >
                <IconYoutube />
            </a>
        </li>
    </ul>
</template>

<style scoped>
.nav__social {
    display: flex;
    list-style: none;
    padding: 8px 64px;
    justify-content: space-around;
    align-items: center;
}

.nav__social-link {
    width: 60px;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 50%;
    background-color: var(--color-white);
    transition: all .3s;
}

@media (min-width: 980px) {

    .nav__social {
        width: fit-content;
    }
    .nav__social-link:hover {
        background-color: var(--color-border-light);
    }

    .nav__social-link svg {
        transition: fill .3s;
    }

    .nav__social-link:hover svg {
        fill: var(--text-color-secondary);
    }
}
</style>