<template>
  <div>
    <!-- edit fingerprint -->
    <v-card color="transparent" elevation="0" href="/profile">
      <v-banner class="padd" color="transparent" elevation="0" single-line>
        <v-icon>mdi-fingerprint</v-icon>
        แก้ไขลายเซ็น
        <template #actions>
          <v-icon>mdi-chevron-left</v-icon>
        </template>
      </v-banner>
    </v-card>
    <v-form class="text-right padd2 drop">
      <v-file-input label="แก้ไขลายเซ็น" filled prepend-icon="mdi-email" />
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
export default {
  layout: 'bgw',
  methods: {
    NextPf () {
      console.log('next profile')
      this.id = this.$route.query.id
      this.$router.push('/profile?id=' + this.id)
    }
  }
}
</script>
