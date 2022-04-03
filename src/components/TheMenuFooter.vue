<script setup>

const itemsNav = [
    {
        title: "Partenaires en affaires",
        items: [
            {
                title: "Nos services",
                link: "/",
            },
            {
                title: "Vos besoins",
                link: "/",
            },
            {
                title: "Nos conseils",
                link: "/",
            },
        ]
    },
    {
        title: "Accès",
        items: [
            {
                title: "Nos experts",
                link: "/",
            },
            {
                title: "Nos bureaux",
                link: "/",
            },
            {
                title: "Nos événements",
                link: "/",
            },
            {
                title: "Actualités | Médias",
                link: "/",
            },
            {
                title: "Le planiguide fiscal",
                link: "/",
            },
            {
                title: "Paiement en ligne",
                link: "/",
            },
        ]
    },
    {
        title: "À propos",
        items: [
            {
                title: "Qui sommes-nous?",
                link: "/",
            },
            {
                title: "Gouvernance",
                link: "/",
            },
            {
                title: "Notre réseau",
                link: "/",
            },
            {
                title: "Protection des données",
                link: "/",
            },
            {
                title: "Nous joindre",
                link: "/",
            },
        ]
    },
    {
        title: "Travailler chez Raymond Chabot Grant Thornton",
        items: [
            {
                title: "Carrières",
                link: "/",
            },
            {
                title: "Nouveaux CPA",
                link: "/",
            },
            {
                title: "CPA d’expérience",
                link: "/",
            },
            {
                title: "Autres professions",
                link: "/",
            },
            {
                title: "Postes ouverts",
                link: "/",
            },

        ]
    },
]

</script>

<template>
        <ul class="footer__list">
            <li v-for="item in itemsNav" :key="item.title" class="footer__item">
                <span class="footer__title">{{ item.title }}</span>
                <ul class="footer__sublist">
                    <li v-for="subitem in item.items" :key="subitem.title" class="footer__subitem">
                        <a :href="subitem.link" class="footer__sublink">{{ subitem.title }}</a>
                    </li>
                </ul>
            </li>
        </ul>
</template>

<style scoped>

ul {
    list-style: none;
    padding: 0;
}

a {
    text-decoration: none;
}

.footer__list {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
}

.footer__item {
    flex: 1;
}
.footer__title {
    font-size: var(--font-size-medium);
    line-height: 1.3;
    font-weight: 500;
    color: var(--text-color-soft);
}

.footer__sublist {
    margin-top: 8px;
}

.footer__sublink {
    font-size: var(--font-size-base);
    color: var(--text-color-mute);
    transition: color 0.35s;
    font-weight: 500;
    line-height: 1.8;
}

.footer__sublink:hover {
    color: var(--text-color-dark);
}

</style>