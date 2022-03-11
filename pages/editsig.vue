<template>
  <div>
    <!-- edit signature -->
    <v-card color="transparent" elevation="0">
      <v-banner class="padd" color="transparent" elevation="0" single-line>
        <v-icon>mdi-fingerprint</v-icon>
        แก้ไขลายเซ็น
        <template #actions>
          <v-icon>mdi-chevron-left</v-icon>
        </template>
      </v-banner>
    </v-card>
    <br>
    <div class="text-center">
      <img :src="signature" width="100px">
    </div>
    <v-form class="text-right padd2 drop">
      <v-file-input
        label="แก้ไขลายเซ็น"
        prepend-icon="mdi-camera"
        filled
        @change="handleFileUpload"
      />
      <v-text-field
        label="Password"
        placeholder="รหัสผ่านของคุณ"
        prepend-icon="mdi-key"
      />
      <v-btn class="top drop" color="normal" @click="NextPf">
        cancel
      </v-btn>
      <v-btn class="top drop" color="indigo" dark>
        save
      </v-btn>
    </v-form>
  </div>
</template>

<script>
// import axios from 'axios'
export default {
  layout: 'bgw',
  data: () => ({
    dialog: false,
    dialog_false: false,
    id: '',
    signature: '',
    password: '',
    file: ''
  }),
  async created () {
    console.log('show techer')
    this.id = this.$route.query.id
    const res = await fetch('http://localhost:7000/list_sig?id=' + this.id)
    const data = await res.json()
    console.log('=', data.datas)
    this.id = data.datas[0].id
    this.signature = data.datas[0].signature
  },
  methods: {
    // async submitFile () {
    //   const formData = new FormData()
    //   formData.append('file', this.$refs.file.files[0])
    //   const res = await axios.post('http://localhost:7000/imgup', formData, {
    //     headers: {
    //       'Content-Type': 'multipart/form-data'
    //     }
    //   })
    //   console.log('ress=', res)
    // },
    // handleFileUpload (e) {
    //   // this.file = this.$refs.file.files[0]
    //   const image = e.target.files[0]
    //   const reader = new FileReader()
    //   reader.readAsDataURL(image)
    //   reader.onload = (e) => {
    //     this.file = e.target.result
    //     console.log('file', this.file)
    //   }
    //   console.log('file', this.file)
    // },
    NextPf () {
      console.log('next profile')
      this.id = this.$route.query.id
      this.$router.push('/profile?id=' + this.id)
    }
  }
}
</script>
