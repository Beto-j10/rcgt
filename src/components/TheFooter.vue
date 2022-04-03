<script setup>
import IconMail from './icons/IconMail.vue';
import IconPhone from './icons/IconPhone.vue';
import TheMainFooter from './TheMainFooter.vue';
import IconGrantThornton from './icons/iconGrantThornton.vue';

</script>

<template>
    <div class="footer__container">
        <div class="footer__contact">
            <div class="footer__contact-means footer__pe">
                <a href="tel:1-866-692-1192" class="footer__contact-btn" aria-label="Telephone">
                    <IconPhone />1 866 686-8167
                </a>
                <a
                    href="/"
                    class="footer__contact-btn footer__contact-btn--fill"
                    aria-label="Link to Contact page"
                >
                    <IconMail />Nous joindre
                </a>
            </div>
            <div class="footer__contact-means footer__subscribe">
                <p class="footer__subscribe-title">Restez à l'affût avec nos infolettres</p>
                <a
                    href="/"
                    class="footer__contact-btn"
                    aria-label="Subscribe to newsletter"
                >Je m'abonne</a>
            </div>
        </div>
        <div class="footer__bottom">
            <div class="footer__nav">
                <div class="footer__main">
                    <TheMainFooter />
                </div>
            </div>
            <div class="footer__copyright">
                <span class="footer__text">Firme membre de :</span>
                <a class="footer__logo" href="/" aria-label="Link to grantthornton global page">
                    <IconGrantThornton />
                </a>
                <span
                    class="footer__text"
                >© 2022 Raymond Chabot Grant Thornton. S.E.N.C.R.L. et ses sociétés affiliées - Tous droits réservés</span>
            </div>
        </div>
    </div>
</template>

<style scoped>
a {
    text-decoration: none;
}
.footer__contact {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.footer__contact-means {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 12px;
    align-items: center;
    font-size: var(--font-size-x-base);
    font-weight: 500;
    color: var(--text-color-secondary-dark);
    text-decoration: none;
    padding: 32px 0;
    width: 100%;
}

.footer__contact-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    font-size: inherit;
    text-decoration: inherit;
    color: inherit;
    font-weight: inherit;
    width: 180px;
    height: 55px;
    border-radius: var(--border-radius);
    background-color: var(--color-white);
    transition: color 0.5s cubic-bezier(0.215, 0.61, 0.355, 1),
        background-color 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.footer__subscribe {
    background-color: var(--color-background-dark-soft);
}

.footer__contact-btn:hover {
    background-color: var(--color-background-dark);
    color: var(--text-color-light);
}

.footer__contact-btn:hover svg {
    stroke: white;
    transition: stroke 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.footer__contact-btn--fill:hover svg {
    fill: white;
    transition: fill 0.5s cubic-bezier(0.215, 0.61, 0.355, 1);
}

.footer__subscribe-title {
    font-size: var(--font-size-x-larger);
    font-weight: 400;
    color: var(--text-color-dark);
    text-align: center;
    width: 60%;
}

.footer__nav {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    padding: 40px 0;
    margin: 0 120px;
    background-color: var(--color-white);
    border-bottom: 1px solid var(--color-background-dark-soft);
}

.footer__main {
    width: 100%;
    display: none;
}
.footer__nav-link {
    color: var(--text-color-mute);
    font-size: 1.78rem;
    transition: color 0.35s;
}
.footer__nav-link:hover {
    color: var(--text-color-dark);
}

.footer__bottom {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: var(--color-white);
    padding: 0 15px;
}

.footer__copyright {
    display: flex;
    gap: 20px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 32px 0 40px;
}

.footer__text {
    font-size: 1.45rem;
    color: var(--text-color-soft);
    text-align: center;
    padding: 0 40px;
}

@media (min-width: 481px) {
    .footer__pe {
        background-color: var(--text-color-secondary-dark);
    }
}

@media (min-width: 980px) {
    .footer__contact {
        flex-direction: row;
    }

    .footer__contact-means {
        height: 165px;
        flex-direction: row;
    }
    .footer__subscribe-title {
        font-size: 1.55rem;
    }

    .footer__bottom {
        padding: 0 30px;
    }

    .footer__main {
        display: initial;
    }

    .footer__copyright {
        flex-flow: row wrap;
        justify-content: start;
    }
}
</style>