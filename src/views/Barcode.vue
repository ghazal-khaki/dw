<template>
  <div class=" barcode">
    <topPopUp
      text="بارکد وارد شده صحیح نمیباشد"
      v-if="error"
    />
    <div id="dynamicPart">
      <img
        class="digilogo"
        src="../assets/Digiwash.png"
        srcset="../assets/Digiwash@2x.png 2x, /../Digiwash@3x.png 3x"
      >
      <img
        src="../assets/Img.png"
        class="image"
      >
      <p class="text2">بارکد شما با موفقیت ثبت شد برای استفاده از بن خود بر روی دکمه زیر کلیک نمایید</p>
    </div>

    <div v-if="isReadingBarcode">
      <div class="read-barcode">
        <button class="camera"><span class="flaticon-dslr-camera"></span></button>
        <input
          @focus="keyBoardIsOn"
          @focusout="keyBoardIsOff"
          placeholder="بارکد"
          class="barcode-value"
          type="text"
          v-model="barcode"
        >
      </div>
      <button
        @click="agree"
        class="agree2"
      >تایید</button>
    </div>

    <div v-if="!isReadingBarcode">
      <input
        value="JW12545876683121                 شماره فاکتور"
        class="agree2 secondInput"
        type="text"
      >
      <button
        @click="useBon"
        class="agree2"
      >استفاده از بن</button>
    </div>
    <bottomPopUp
    v-if="true"
    mode="agreement"
    />
      <!-- :mode="mode" -->
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/barcode.sass'
import topPopUp from '../components/topPopUp'
import bottomPopUp from '../components/bottomPopUp'
import { setTimeout } from 'timers';

export default {
  name: 'barcode',
  data () {
    return {
      barcode: null,
      error: false,
      isReadingBarcode: true,
      bottomPopUp:false,
      mode: 0,
    }
  },
  computed: {

  },
  components: {
    topPopUp,
    bottomPopUp
  },
  methods: {
    keyBoardIsOn () {
      document.getElementById('dynamicPart').classList.add('resize')
    },
    keyBoardIsOff () {
      document.getElementById('dynamicPart').classList.remove('resize')
    },
    agree () {
      if (this.barcode === 'abcd') {
        this.isReadingBarcode = false
      } else {
        this.error = true
        setTimeout(() => {
          this.error = false
        }, 3000)
      }
    },
    useBon () {
      this.mode = 'agreement'
      this.bottomPopUp = true
    }
  },
}
</script>
