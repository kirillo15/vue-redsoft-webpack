<template>
    <div>
        <button class="btn">
        {{content}}
        </button>
    </div>
</template>

<script>
export default {
    name: 'button',
    props: {
        content: String
    },
}
</script>

<style lang="scss">
    .btn {
        position: relative;
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
        padding: 13px 37px;
        transition: .3s;

        &:hover {
            background: #776763;
            transition: .3s;
        }
    }


</style>