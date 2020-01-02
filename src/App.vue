<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>
<style lang="sass">
@import './assets/font/flaticon.css'
@import './assets/WebFonts/css/fontiran.css'
html
  height: 100%

body
  margin: 0px
  background-image: url(./assets/BG.jpg)
  background-size: cover
  object-fit: contain
  // background-image: -webkit-image-set(url(./assets/BG@2x.jpg) 2x, url(./assets/BG@3x.jpg) 3x)
  // background-image: image-set(url(./assets/BG@2x.jpg) 2x, url(./assets/BG@3x.jpg) 3x)
  font-family: iranyekan !important // iranyekanwebregular, sans-serif

button
  font-family: iranyekan

input
  font-family: iranyekan !important

input::placeholder
  font-family: iranyekan !important
</style>