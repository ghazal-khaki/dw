<template>
  <div class="home">
    <topPopUp
    text="رمزعبور وارد شده صحیح نمیباشد"
    v-if="error" />
    <img
      class="digilogo"
      src="../assets/Digiwash.png"
      srcset="../assets/Digiwash@2x.png 2x, /../Digiwash@3x.png 3x"
    >
    <div class="enterForm">
        <input
          placeholder="نام کاربری"
          class="inputSize userName"
          type="text"
          name=""
          id=""
        >
        <label for="password"></label>
        <input
          placeholder="رمز عبور"
          class="inputSize password"
          type="password"
          name="password"
          id=""
        >
        <div class="checkbox">
          <label for="checkbox">مرا به خاطر بسپار</label>
          <input
            type="checkbox"
            name="checkbox"
            id=""
          >
        </div>
        <button
          class="inputSize submit"
        >ورود</button>
      <p class="text">هر رفع هرگونه مشکل و پشتیبانی با شماره تلفن <span class="phoneNumber">۰۲۱۴۵۱۸۳۰۰۰</span>تماس بگیرید</p>
    </div>
    <bottomPopUp
    v-if="true"
    mode="success"/>
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'
import topPopUp from '../components/topPopUp'
import bottomPopUp from '../components/bottomPopUp'
export default {
  name: 'home',
  data() {
    return {
      error: false
    }
  },
  components: {
    topPopUp,
    bottomPopUp
  }
}
</script>
