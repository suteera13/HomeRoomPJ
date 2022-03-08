<template>
  <div>
    <!-- edit fingerprint -->
    <v-card color="transparent" elevation="0">
      <v-banner class="padd" color="transparent" elevation="0" single-line>
        <v-icon>mdi-email-edit</v-icon>
        แก้ไขอีเมล์
        <template #actions>
          <v-icon>mdi-chevron-left</v-icon>
        </template>
      </v-banner>
    </v-card>
    <div class="padd2 drop">
      <v-text-field
        v-model="email"
        label="email"
        prepend-icon="mdi-email"
      />
      <v-text-field
        v-model="password"
        label="password"
        prepend-icon="mdi-key"
      />
      <div class="text-right">
        <v-btn class="top drop" color="normal">
          cancel
        </v-btn>
        <v-btn class="top drop" color="indigo" dark @click="SaveMail">
          save
        </v-btn>
      </div>
    </div>

    <!-- dialog -->
    <div>
      <v-dialog v-model="dialog" width="220">
        <v-card>
          <v-card light class="padd text-center" elevation="0">
            <v-icon large left color="indigo">
              mdi-check-circle-outline
            </v-icon>
            ต้องการบันทึกหรือไม่
          </v-card>
          <div class="padd text-center">
            <v-btn text @click="dialog = false">
              ไม่
            </v-btn>
            <v-btn text @click="dialog = false">
              ใช่
            </v-btn>
          </div>
        </v-card>
      </v-dialog>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'bgw',
  data: () => ({
    dialog: false,
    email: '',
    password: ''
    // firstname: '',
    // lastname: ''
  }),
  async created () {
    console.log('show techer')
    this.id = this.$route.query.id
    const res = await fetch('http://localhost:7000/list_tch?id=' + this.id)
    const data = await res.json()
    console.log('=', data.datas)
    this.email = data.datas[0].email
    // this.firstname = data.datas[0].firstname
    // this.lastname = data.datas[0].lastname
    // this.password = data.datas[0].password
  },
  methods: {
    SaveMail () {
      this.dialog = true
      setInterval(() => {
        this.dialog = false
      }, 10000)
    },
    async SaveConfirm () {
      const save = {
        email: this.email,
        password: this.password
      }
      const res = await fetch('http://localhost:7000/edit_mail?id=', save)
      console.log(res.data)
      if (res.data.status === 1) {
        this.$router.push('/profile?id=' + this.id)
      }
    }
  }
}
</script>
