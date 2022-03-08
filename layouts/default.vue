<template>
  <v-app class="bg2">
    <div>
      <v-container>
        <Nuxt />
      </v-container>
      <v-bottom-navigation
        color="indigo"
        absolute
      >
        <v-btn @click="NextHome">
          <span>หน้าแรก</span>
          <v-icon>mdi-home</v-icon>
        </v-btn>

        <v-btn @click="NextNote">
          <span>บันทึก</span>
          <v-icon>mdi-content-save</v-icon>
        </v-btn>

        <v-btn @click="NextConfirm">
          <span>รับรอง</span>
          <v-icon>mdi-text-box-check</v-icon>
        </v-btn>

        <v-btn @click="NextReport">
          <span>รายงาน</span>
          <v-icon>mdi-text-box</v-icon>
        </v-btn>
      </v-bottom-navigation>
    </div>
  </v-app>
</template>

<script>
export default {
  data: () => ({

  }),
  created () {
    this.ShowMenu()
  },
  methods: {
    ShowMenu () {
      console.log('show menu')
      this.id = this.$route.query.id
    },
    NextPf () {
      console.log('next profile')
      this.id = this.$route.query.id
      this.$router.push('/profile?id=' + this.id)
    },
    NextHome () {
      console.log('next home')
      this.$router.push('/home?id=' + this.id)
    },
    NextNote () {
      console.log('next note')
      this.$router.push('/note?id=' + this.id)
    },
    NextConfirm () {
      console.log('next confirm')
      this.$router.push('/confirm?id=' + this.id)
    },
    NextReport () {
      console.log('next report')
      this.$router.push('/report?id=' + this.id)
    }
  }
}
</script>

<style>
.bg2{
  background-color: #fff;
  background-attachment: fixed;
  height: 100%;
}
.box2{
  padding: 40px;
}
.text1{
  font-family: "FC Minimal";
  font-size: 34px;
  color: #000;
  margin-top: -5%;
}
.text2{
  font-family: "FC Minimal";
  font-size: 16px;
  color: #000;
  margin-top: -20px;
}
.text3{
  font-family: "FC Minimal";
  color: #000;
  font-size: 18px;
  margin-left: 14px;
}
.text4{
  font-family: "FC Minimal";
  font-size: 26px;
  color: #000;
}
.text5{
  font-family: "FC Minimal";
  font-size: 16px;
  color: #000;
  margin-top: -10px;
}
.padd{
  padding: 10px;
}
.padd2{
  padding: 20px;
}
.drop{
  margin-top: 20px;
}
.drop2{
  margin-top: 10px;
}
.top{
  margin-top: 50px;
}
.up{
  margin-top: -70px;
}
.up2{
  margin-top: -10px;
}
.up3{
  margin-top: -20px;
}
.menu{
  margin-left: 20px;
}
</style>
