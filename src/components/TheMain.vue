<template>
    <div>
        <section class="event">
            <div class="banner">
                asdf
                asdfas
                df
                <br />as
                <br />df
                <br />a
                <br />
            </div>
            <div class="event__content">
                <div class="event__subscribe"></div>
                <div class="event__info"></div>
            </div>
        </section>
    </div>
</template>

<style scoped>
.banner {
    background-image: url("https://www.rcgt.com/app/uploads/2021/03/shack_1440x470.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    height: 720px;
}

.banner::after {
    content: "";
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    width: 100%;
    height: 100%;
    position: absolute;
    background: linear-gradient(
        to right,
        rgba(117, 55, 207, 0.98) 0,
        rgba(117, 55, 207, 0.065) 100%
    );
}

@media (min-width: 1025px) {
    .banner {
        height: 480px;
    }
}
</style>