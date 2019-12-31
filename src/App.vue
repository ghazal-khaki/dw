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
html
  height: 100%

body
  margin: 0px
  font-family: IRANYekanFaNum,sans-serif
  background-image: url(./assets/BG.jpg)
  background-size: cover
  object-fit: contain
  background-image: -webkit-image-set(url(./assets/BG@2x.jpg) 2x, url(./assets/BG@3x.jpg) 3x)
  background-image: image-set(url(./assets/BG@2x.jpg) 2x, url(./assets/BG@3x.jpg) 3x)

</style>