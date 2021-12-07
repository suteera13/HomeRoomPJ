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
        Log In
      </p>
    </div>
    <p class="text3">
      กรุณาล็อกอินเข้าสู่ระบบ
    </p>
    <div class="boxin text-center">
      <v-form>
        <v-text-field v-model="user" label="Name" />
        <v-text-field v-model="pass" label="Password" />
        <v-checkbox label="Remember password" />
        <div style="color: #37474F; font-size: 24px;font-family: FC Minimal;">
          <p class="btn2" @click="onSave">
            Log In
          </p>
        </div>
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

<script>
export default {
  data: () => ({
    user: '',
    pass: ''
  }),
  methods: {
    async onSave () {
      console.log('onSave')
      const res = await fetch('http://localhost:7001/list?user=' +
      this.user + '&pass=' + this.pass)
      const data = await res.json()
      console.log('data=', data)
    }
  }
}
</script>
