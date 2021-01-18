<template>
    <div class="footer">
        <div class="container">
            <div class="footer-wrap">
                <div class="footer__left">
                    <Logo/>
                    <Nav/>
                </div>
                <div class="footer-contact">
                    <div class="footer-contact__item">
                        <img src="/src/assets/phone.png" alt="">
                        <a href="tel:+74955555555" class="footer__link">+7 (495) 555-55-55</a>
                    </div>
                    <div class="footer-contact__item">
                        <img src="/src/assets/local.png" alt="">
                        <a href="#" class="footer__link">г. Москва, ул. Расплетина, 24</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Logo from './Logo.vue'
import Nav from './Nav.vue'

export default {
    name: 'footer',
    components: {
        Logo,
        Nav
    },
    data: () => ({
        footerContact: [
            {
                title: '+7 (495) 555-55-55'
            }
        ]
    })
}
</script>

<style lang="scss">
    .footer {

        &-wrap {
            display: flex;
            justify-content: space-between;
        }

        &__link {
            text-decoration: none;
        }

        &-contact {
            display: flex;
            align-items: center;
        }

        &__link {
            font-family: Merriweather;
            font-style: normal;
            font-weight: normal;
            font-size: 14px;
            line-height: 150%;
            color: #555555;
        }

        &__left {
            display: flex;
        }

        &-contact__item {
            margin: 0 30px 0 0px;
        }
    }
</style>