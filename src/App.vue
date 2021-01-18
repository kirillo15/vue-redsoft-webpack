<template>
  <div id="app">
    <Header/>
    <PictureWrap/>
    <Footer/>
  </div>
</template>

<script>
import Header from './views/Header.vue'
import PictureWrap from './views/PictureWrap.vue'
import Footer from './views/Footer.vue'
export default {
  name: 'app',
  components: {
    Header,
    PictureWrap,
    Footer
  },
  data: () => ({

  })
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Merriweather&display=swap');

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Merriweather;
  background: #E5E5E5;
}

.container {
  max-width: 1216px;
  width: 100%;
  margin: 0 auto;
}

</style>
