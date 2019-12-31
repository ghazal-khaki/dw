<template>
  <div class="top-pop-up">
    <p class="pop">{{text}}</p>
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'

export default {
  name: 'topPopUp',
  props: {
    text: String
    }
}
</script>
<style lang="sass">
.top-pop-up
  position: fixed
  width: 100%
  height: 60px
  background-color: white
  p
    margin: 0px
    color: rgb(226,24,24)
    text-align: center
    padding-top: 18px
</style>
