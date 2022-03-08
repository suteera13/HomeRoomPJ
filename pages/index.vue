<template>
  <div class="text-center">
    <p>
      <v-img src="../img/logoW.png" class="img" />
    </p>
    <br>
    <v-btn class="index2" color="normal" href="/login" rounded>
      LogIn <v-icon>mdi-chevron-right</v-icon>
    </v-btn>
  </div>
</template>

<script>
export default {
  layout: 'BGb'
}
</script>

<style>
.index2{
  margin-top: 40%;
}
.img{
  width: 140px;
  margin: auto;
  margin-top: 70%;
}
</style>
