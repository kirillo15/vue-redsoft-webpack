<template>
    <div>
        <header class="header">
            <div class="container">
                <div class="header-wrap">
                    <div class="header__left">
                        <Logo/>
                        <Nav/>
                    </div>
                    <Search/>
                </div>
            </div>
        </header>
    </div>
</template>

<script>
import Search from './Search.vue'
import Nav from './Nav.vue'
import Logo from './Logo.vue'

export default {
    name: 'header',
    data: () => ({
        navItem: ['Каталог', 'Доставка', 'Оплата', 'Контакты', 'О галерее'],
        
    }),
    components: {
        Search,
        Nav,
        Logo
    }
}
</script>

<style lang="scss">
    .header {

        margin: 0 0 49px;
        border-bottom: 1px solid #ccc;
        padding: 0 0 19px 0;

        &-wrap {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20px 0 0;
        }

        & .logo {
            cursor: pointer;
        }

        &__left {
            display: flex;
            align-items: center;
        }
    }

</style>