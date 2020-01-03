<template>
  <div class="home">
    <topPopUp
      text="رمزعبور وارد شده صحیح نمیباشد"
      v-if="error"
    />
    <img
      class="digilogo"
      src="../assets/Digiwash.png"
      srcset="../assets/Digiwash@2x.png 2x, /../Digiwash@3x.png 3x"
    >
    <div class="enterForm">
      <!-- // -->
      <span
        v-if="conditionForUsername"
        class="label-username"
      >نام کاربری</span>
      <input
        @focus="usernameFocused = true"
        @blur="usernameFocused = false"
        placeholder="نام کاربری"
        class="inputSize userName"
        type="text"
        v-model="username"
        name=""
        id=""
      >
      <span
        v-if="conditionForPassword"
        class="label-password"
      >رمز عبور</span>
      <span
        v-if="conditionForPassword"
        class="eye flaticon-hide"
        @click="showPassword"
      ></span>
      <input
        @focus="focus = true"
        placeholder="رمز عبور"
        class="inputSize password"
        type="password"
        name="password"
        v-model="password"
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
      <button class="inputSize submit">ورود</button>
      <p class="text">هر رفع هرگونه مشکل و پشتیبانی با شماره تلفن <span class="phoneNumber">۰۲۱۴۵۱۸۳۰۰۰</span>تماس بگیرید</p>
    </div>
    <bottomPopUp
      v-if="false"
      mode="agreement"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'
import topPopUp from '../components/topPopUp'
import bottomPopUp from '../components/bottomPopUp'
export default {
  name: 'home',
  data () {
    return {
      showingPassword: false,
      password: null,
      username: null,
      usernameFocused: false,
      passwordFocused: false,
      error: false,
      passHasBeenFocused: false,
      passShouldBeFocused: false,
      showingPassIcon: false,
      focus: false
    }
  },
  components: {
    topPopUp,
    bottomPopUp
  },
  computed: {
    conditionForUsername () {
      return this.usernameFocused || this.username
    },
    conditionForPassword () {
      return this.password || this.focus
    }
  },
  watch: {
    'conditionForUsername': {
      handler (newValue) {
        if (newValue) {
          document.getElementsByClassName('userName')[0].classList.add('username-visible')
          document.getElementsByClassName('userName')[0].placeholder = ''
        } else {
          document.getElementsByClassName('userName')[0].classList.remove('username-visible')
          document.getElementsByClassName('userName')[0].placeholder = 'نام کاربری'
        }
      }
    },
    'conditionForPassword': {
      handler (newValue) {
        if (newValue) {
          document.getElementsByClassName('userName')[0].classList.add('password-visible')
          document.getElementsByClassName('password')[0].classList.add('password-visible2')
          document.getElementsByClassName('password')[0].placeholder = ''
        } else {
          document.getElementsByClassName('userName')[0].classList.remove('password-visible')
          document.getElementsByClassName('password')[0].classList.remove('password-visible2')
          document.getElementsByClassName('password')[0].placeholder = 'رمز عبور'
        }
      }
    }
  },
  methods: {
    showPassword () {
      document.getElementsByClassName('password')[0].focus()
      this.showingPassword = !this.showingPassword
      if (this.showingPassword) {
        document.getElementsByClassName('eye')[0].classList.remove('flaticon-hide')
        document.getElementsByClassName('eye')[0].classList.add('flaticon-eye')
        document.getElementsByClassName('password')[0].type = "text"
      } else {
        document.getElementsByClassName('eye')[0].classList.remove('flaticon-eye')
        document.getElementsByClassName('eye')[0].classList.add('flaticon-hide')
        document.getElementsByClassName('password')[0].type = "password"
      }
    },
  },
  updated () {

    if (conditionForPassword) {

    }
  }
}
</script>
