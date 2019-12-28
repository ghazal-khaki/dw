<template>
  <div class="home">
    <img
      class="digilogo"
      src="../assets/Digiwash.png"
      srcset="../assets/Digiwash@2x.png 2x, /../Digiwash@3x.png 3x"
    >
    <div class="enterForm">
      <form>
        <input placeholder="نام کاربری" class="inputSize userName" type="text" name="" id="">
        <label for="password"></label>
        <input placeholder="رمز عبور" class="inputSize password" type="password" name="password" id="">
        <div>
          <label for="checkbox"></label>
        <input type="checkbox" name="checkbox" id="">
        </div>
        <input class="inputSize submit" type="submit" value="ورود">
      </form>
      <p class="text">هر رفع هرگونه مشکل و پشتیبانی با شماره تلفن  <span class="phoneNumber">۰۲۱۴۵۱۸۳۰۰۰</span>تماس بگیرید</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import '../style/home.sass'

export default {
  name: 'home'
}
</script>
