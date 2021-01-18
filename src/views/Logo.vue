<template>
    <div class="logo">
        <img :src="src" alt="">
    </div>
</template>

<script>
export default {
    name: 'logo',
    data: () => ({
        src: 'src/assets/Group.png'
    })
}
</script>