<template>
  <div class="text-center">
    <v-alert color="indigo lighten-1" height="200px" />
    <v-card color="transparent" elevation="0">
      <v-badge color="indigo" icon="mdi-pen" bordered overlap>
        <v-avatar class="up" size="100px">
          <v-img src="../img/ava2.jpg" />
        </v-avatar>
      </v-badge>
    </v-card>
    <v-banner>
      <p class="text4">
        <strong>{{ firstname }} {{ lastname }}</strong>
      </p>
      <p class="text5">
        {{ email }}
      </p>

      <!-- <br><br>
      <v-hover v-slot="{ hover }">
        <v-img src="../img/logoB.png" max-width="150px" max-height="100px" style="margin: auto;">
          <v-expand-transition>
            <div
              v-if="hover"
              class="indigo v-card--reveal text-h3 white--text"
              style="height: 100%;"
            >
              ลายเซ็น
            </div>
          </v-expand-transition>
        </v-img>
      </v-hover> -->
    </v-banner>
    <div class="text-left">
      <!-- edit Email -->
      <v-card color="transparent" elevation="0" @click="NextEdit">
        <v-banner class="padd" color="transparent" elevation="0" single-line>
          <v-icon>mdi-email-edit</v-icon>
          แก้ไขอีเมล์
          <template #actions>
            <v-icon>mdi-chevron-right</v-icon>
          </template>
        </v-banner>
      </v-card>
      <!-- edit fingerprint -->
      <v-card color="transparent" elevation="0" href="/editsig">
        <v-banner class="padd" color="transparent" elevation="0" single-line>
          <v-icon>mdi-fingerprint</v-icon>
          แก้ไขลายเซ็น
          <template #actions>
            <v-icon>mdi-chevron-right</v-icon>
          </template>
        </v-banner>
      </v-card>
      <!-- back home -->
      <v-card color="transparent" elevation="0">
        <v-banner class="padd" color="transparent" elevation="0" single-line>
          <v-icon>mdi-home</v-icon>
          หน้าแรก
          <template #actions>
            <v-icon>mdi-chevron-right</v-icon>
          </template>
        </v-banner>
      </v-card>
      <!-- log uot -->
      <v-card href="/" color="transparent" elevation="0">
        <v-banner class="padd" color="transparent" elevation="0" single-line>
          <v-icon>mdi-logout</v-icon>
          ออกจากระบบ
          <template #actions>
            <v-icon>mdi-chevron-right</v-icon>
          </template>
        </v-banner>
      </v-card>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'bgw',
  data: () => ({
    id: '',
    email: '',
    firstname: '',
    lastname: ''
  }),
  created () {
    this.ShowPf()
  },
  methods: {
    async ShowPf () {
      console.log('show techer')
      this.id = this.$route.query.id
      const res = await fetch('http://localhost:7000/list_tch?id=' + this.id)
      const data = await res.json()
      console.log('techer=', data.datas[0])
      this.id = data.datas[0].id
      this.lastname = data.datas[0].lastname
      this.firstname = data.datas[0].firstname
      this.email = data.datas[0].email
    },
    NextEdit (id) {
      console.log('id=', this.id)
      this.$router.push('/editmail?id=' + this.id)
    },
    NextHome () {
      console.log('next home')
      this.$router.push('/home?id=' + this.id)
    }
  }
}
</script>
