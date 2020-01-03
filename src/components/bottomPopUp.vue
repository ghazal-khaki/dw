<template>
  <div class="bottom-pop-up">
    <p class="header">{{header}}</p>
    <p class="text">{{text}}</p>
    <div
      v-if="localMode!=='agreement'"
      class="buttons"
    >
      <button class="bigButton">{{buttonValue}}</button>
    </div>
    <div
      class="buttons"
      v-if="localMode==='agreement'"
    >
      <button class="agree">تایید</button>
      <button class="cancel">انصراف</button>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'

export default {
  name: 'bottomPopUp',
  data () {
    return {
      localMode: this.mode
    }
  },
  props: {
    mode: String
  },
  computed: {
    header () {
      // console.log(this.mode)
      if (this.localMode === 'success') {
        return 'بن شما با موفقیت ثبت شد'
      } else if (this.localMode === 'failure') {
        return 'متاسفانه بن ثبت نشد'
      } else {
        return 'تایید استفاده از بن'
      }
    },
    text () {
      if (this.localMode === 'success') {
        return 'برای بازگشت به صفحه اصلی روی دکمه زیر کلیک نمایید'
      } else if (this.localMode === 'failure') {
        return 'متاسفانه حین انجام عملیات مشکلی رخ داده لطفا دوباره تلاش نمایید'
      } else {
        return 'شما درخواست استفاده از بن را کرده اید از این درخواست اطمینان دارید'
      }
    },
    buttonValue () {
      if (this.localMode === 'success') {
        return 'بازگشت به صفحه اصلی'
      } else if (this.localMode === 'failure') {
        return 'بازگشت به صفحه اصلی'
      }
    }
  },
  mounted () {
    if (this.localMode === 'success' && document.getElementsByClassName('header')) {
      document.geplaceholdertElementsByClassName('header')[0].style.color = 'rgb(34,174,48)'
      document.getElementsByClassName('bigButton')[0].style.backgroundColor = 'rgb(34,174,48)'
    } else if (this.localMode === 'failure' && document.getElementsByClassName('header')) {
      document.getElementsByClassName('header')[0].style.color = 'rgb(226,24,24)'
      document.getElementsByClassName('bigButton')[0].style.backgroundColor = 'rgb(226,24,24)'
    } else if (this.localMode === 'agreement' && document.getElementsByClassName('header')) {
      document.getElementsByClassName('header')[0].style.color = 'rgb(255,95,0)'
      document.getElementsByClassName('cancel')[0].style.color = 'rgb(255,95,0)'
      document.getElementsByClassName('agree')[0].style.backgroundColor = 'rgb(255,95,0,0.44)'
    }
  },
}

</script>
<style lang="sass" scoped >
.bottom-pop-up
  z-index: 10
  bottom: 0px
  position: fixed
  width: 100%
  height: 244px
  background-color: rgb(246,246,246)
  border-radius: 10% 10% 0px 0px
  p
    margin: 0px
    text-align: center

  .header
    font-size: 17px
    padding-top: 18px

  .text
    font-size: 14px
    padding-top: 27px
  
  .buttons
    padding-top: 39px
    display: grid
    grid-auto-flow: column
    justify-content: center
    grid-gap: 12px
    button
      border-radius: 11px
      border: 0px
    .bigButton
      width: 286px
      height: 52px
      color: white
    .cancel
      width: 137px
      height: 52px
      background-color: white
      
    .agree
      width: 137px
      height: 52px
      color: white
</style>
