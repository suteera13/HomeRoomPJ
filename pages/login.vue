<template>
  <div class="box1">
    <h1 class="text2">
      LOG IN
    </h1>
    <br>
    <v-text-field
      label="Username"
      placeholder="ชื่อผู้ใช้ของคุณ"
      filled
    />
    <v-text-field
      label="Password"
      placeholder="รหัสผ่านของคุณ"
      filled
    />
    <v-btn block color="indigo" href="/home" dark>
      Log In
    </v-btn>
  </div>
</template>

<script>
export default {
  deta: () => ({
    user: '',
    pass: '',
    dialog: false,
    dialog_false: false
  }),
  methods: {
    async LogIn () {
      console.log('LogIn')
      const res = await fetch('http://localhost:7001/list?user=' +
      this.user + '&pass=' + this.pass)
      const result = await res.json()
      console.log('data=', result)
      if (result.status > 0) {
        console.log('Login OK')
        this.dialog = true
        setInterval(() => {
          this.dialog = false
          this.$router.push('/home')
        }, 3000)
      } else {
        console.log('Login Error')
        this.dialog_false = true
        setInterval(() => {
          this.dialog_false = false
          this.$router.push('/login')
        }, 3000)
      }
    }
  }
}
</script>
