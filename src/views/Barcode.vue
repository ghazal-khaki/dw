<template>
  <div class="barcode">
    <img
      class="digilogo"
      src="../assets/Digiwash.png"
      srcset="../assets/Digiwash@2x.png 2x, /../Digiwash@3x.png 3x"
    >
    <img src="../assets/Img.png" class="image">
    <p class="text2">بارکد شما با موفقیت ثبت شد برای استفاده از بن خود بر روی دکمه زیر کلیک نمایید</p>

  </div>
</template>

<script>
// @ is an alias to /src
import '../style/barcode.sass'

export default {
  name: 'barcode'
}
</script>
