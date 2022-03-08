<template>
  <div class="box2">
    <v-img src="../img/logoB.png" class="img2" />
    <br>
    <!-- <p class="text2 text-center">
      กรุณาล็อกอินเข้าสู่ระบบเพื่อใช้งาน
    </p> -->
    <v-form>
      <v-text-field
        v-model="email"
        label="Email"
        placeholder="ชื่อผู้ใช้ของคุณ"
        prepend-icon="mdi-email"
      />
      <v-text-field
        v-model="password"
        label="Password"
        placeholder="รหัสผ่านของคุณ"
        prepend-icon="mdi-key"
      />
      <v-btn class="top drop" block color="indigo" dark @click="Login">
        Log In
      </v-btn>
      <!-- <v-btn class="top drop" block color="indigo" dark href="/home">
        Log In
      </v-btn> -->
    </v-form>

    <!-- ... -->
    <div class="text-center top">
      <v-icon>mdi-dots-horizontal</v-icon>
    </div>

    <!-- dialog1 -->
    <div>
      <v-dialog v-model="dialog" width="200">
        <v-card light class="padd text-center">
          <v-icon large left color="indigo">
            mdi-check-circle-outline
          </v-icon>
          ล็อกอินสำเร็จ
        </v-card>
      </v-dialog>
    </div>

    <!-- dialog2 -->
    <div>
      <v-dialog v-model="dialog_false" width="200">
        <v-card light class="padd text-center">
          <v-icon large left color="error">
            mdi-close-circle-outline
          </v-icon>
          อีเมล์หรือรหัสผ่านไม่ถูกต้อง
        </v-card>
      </v-dialog>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'bgw',
  data: () => ({
    email: '',
    password: '',
    dialog: false,
    dialog_false: false,
    id: ''
  }),
  methods: {
    async Login () {
      console.log('Login')
      const res = await fetch('http://localhost:7000/login_next?email=' +
      this.email + '&password=' + this.password)
      const data = await res.json()
      if (data.status > 0) {
        data.status = 0
        console.log('Login OK')
        console.log('data=', data.data[0])
        this.id = data.data[0].id
        this.dialog = true
        setInterval(() => {
          this.dialog = false
          this.$router.push('/home?id=' + this.id)
        }, 2000)
      } else {
        console.log('Login Error')
        this.dialog_false = true
        setInterval(() => {
          this.dialog_false = false
        }, 3000)
      }
    }
  }
}
</script>

<style>
.img2{
  width: 100px;
  margin: auto;
  margin-top: -10%;
}
</style>
