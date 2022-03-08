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
    <div class="text-right padd2 drop">
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
      <v-btn class="top drop" color="normal">
        cancel
      </v-btn>
      <v-btn class="top drop" color="indigo" dark>
        save
      </v-btn>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'bgw',
  data: () => ({
    email: '',
    password: '',
    firstname: ''
  }),
  async created () {
    console.log('show techer')
    this.id = this.$route.query.id
    const res = await fetch('http://localhost:7000/edit_mail?id=' + this.id)
    const data = await res.json()
    console.log('=', data.datas)
    this.email = data.datas.email
    this.password = data.datas.password
  }

}
</script>
