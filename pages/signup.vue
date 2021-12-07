<template>
  <div class="loginbox">
    <p class="text13 text-center">
      HomeRooM
    </p>
    <p class="text14 text-center">
      C - T - C
    </p>
    <div class="boxon">
      <p class="text2">
        Sign Up
      </p>
    </div>
    <p class="text3">
      กรุณาลงทะเบียนเพื่อเข้าสู่ระบบ
    </p>
    <div class="boxin text-center">
      <v-form>
        <v-text-field label="E-mail" />
        <v-text-field label="Name" />
        <v-text-field label="Department" />
        <v-text-field label="Group" />
        <v-text-field label="Password" />
        <v-text-field label="Confirm password" />
        <nuxt-link to="/login" style="color: #37474F; font-size: 24px;font-family: FC Minimal;">
          <p class="btn2">
            Sign up
          </p>
        </nuxt-link>
        <br>
        <nuxt-link to="/login">
          <p class="text4">
            Log In
          </p>
        </nuxt-link>
      </v-form>
    </div>
  </div>
</template>
