<template>
    <div class="nav">
        <ul class="nav-wrap">
            <li class="nav__item"
            v-for="(item,index) of navItem"
                :key="index"
            >
                <a href="#" class="nav__link">{{item}}</a>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'navr',
    data: () => ({
        navItem: ['Каталог', 'Доставка', 'Оплата', 'Контакты', 'О галерее'],
        // src: 'src/assets/Group.png'
    }),
}
</script>

<style lang="scss">
    .nav {
        &-wrap {
            list-style: none;
            display: flex;
            justify-content: space-between;
            width: 100%;
        }

        &__link {
            text-decoration: none;
            color: #343030;
            font-style: normal;
            font-weight: normal;
            font-size: 14px;
            line-height: 150%;
        }

        &__item {
            margin: 0 41px 0 0;
        }

        &__item:first-child {
            margin: 0 38px 0 8px;
        }

        &__item:last-child {
            margin: 0 0 0 -6px;
        }
    }
</style>