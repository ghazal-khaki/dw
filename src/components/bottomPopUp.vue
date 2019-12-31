<template>
  <div class="bottom-pop-up">
    <p class="header">{{header}}</p>
    <p class="text">{{text}}</p>
    <div class="buttons">
      <button>sddsf</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'

export default {
  name: 'topPopUp',
  data() {
    return {
      header: 'null',
      text: 'null'
    }
  },
  props: {
    mode: String
    }
}
</script>
<style lang="sass">
.bottom-pop-up
  position: fixed
  width: 100%
  height: 244px
  background-color: rgb(246,246,246)
  border-radius: 10% 10% 0px 0px
  p
    margin: 0px
    text-align: center

  .header
    padding-top: 18px

  .text
    padding-top: 27px
  
  .buttons
    padding-top: 39px
    button
      margin: 0% 15.4% 0% 15.4%
      width: 286px
      height: 52px
      border-radius: 11px
      border: 0px
</style>
