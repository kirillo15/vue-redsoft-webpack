<template >
    <div class="search">
        <div class="search-wrap">
            <input type="text" name="search" class="search__input"
            :placeholder="placeholder"
            >
            <Button
            @click.prevent=""
            :content="btnName"
            ></Button>
            
        </div>
    </div>
</template>

<script>
import Button from './Button.vue'

export default {
    name: 'search',
    components: {
        Button
    },
    data: () => ({
        btnName: 'Найти',
        placeholder: 'Поиск по названию картины'
    })
}
</script>

<style lang="scss">
    .search {

        width: 34%;

        &-wrap {
            display: flex;
            align-items: center;
        }
        

        &__input {
            padding: 13px;
            width: 75%;
            border: 1px solid #cccccc70;
            outline: none;
            background: #E5E5E5;
            font-style: normal;
            font-weight: normal;
            font-size: 14px;
            line-height: 150%;
            letter-spacing: 0.08rem;
        }
        &__btn {
            font-family: Merriweather;
            font-style: normal;
            font-weight: bold;
            font-size: 14px;
            line-height: 150%;
            background: #403432;
            color: #fff;
            border: none;
            outline: none;
            cursor: pointer;
            padding: 10px;
        }
    }
</style>