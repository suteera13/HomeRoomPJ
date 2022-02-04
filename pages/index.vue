<template>
  <div>
    <p>
      <v-img src="../img/25.png" class="img" />
    </p>

    <p class="text11 text-center">
      HomeRooM
    </p>
  </div>
</template>

<script>
export default {
  created () {
    this.nextpage()
  },
  methods: {
    nextpage () {
      console.log('nextpage')
      setInterval(() => {
        this.$router.push('/login')
      }, 3000)
    }
  }
}
</script>

<style>
.img{
  width: 80px;
  margin: auto;
  margin-top: 65%;
}
</style>
