<template>
  <div class="loginbox">
    <p class="text11 text-center">
      HomeRooM
    </p>
    <p class="text12 text-center">
      C - T - C
    </p>
    <div class="boxon">
      <p class="text2">
        Log In
      </p>
    </div>
    <p class="text3">
      กรุณาล็อกอินเข้าสู่ระบบ
    </p>
    <div class="boxin text-center">
      <v-form>
        <v-text-field label="Name" />
        <v-text-field label="Password" />
        <v-checkbox label="Remember password" />
        <nuxt-link to="/home" style="color: #37474F; font-size: 24px;font-family: FC Minimal;">
          <p class="btn2">
            Log In
          </p>
        </nuxt-link>
        <br>
        <nuxt-link to="/signup">
          <p class="text4">
            Sign up
          </p>
        </nuxt-link>
      </v-form>
    </div>
  </div>
</template>

<style>
  .text11{
    font-family: "FC Minimal";
    font-size: 24px;
    color: #000;
    margin-top: -5%;
  }
  .text12{
    font-size: 12px;
    word-spacing: 5px;
    color: #BDBDBD;
    margin-top: -10%;
  }
</style>
