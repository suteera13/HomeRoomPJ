<template>
  <v-app>
    <div class="bg2">
      <v-container>
        <Nuxt />
      </v-container>
    </div>
  </v-app>
</template>

<style>
  /* .bg{
    background-image: url("../assets/img/homeroom.png");
    background-attachment: fixed;
    background-size: 100% 100%, auto;
    height: 100%;
  } */
  .bg2{
    background-color: #fff;
    height: 100%;
  }
  .loginbox{
    display: block;
    color: #212121;
    width: 320px;
    height: 500px;
    padding: 40px;
    border-radius: 20px;
    margin: auto;
  }
  .boxon{
    display: block;
    background-color: #000;
    width: 200px;
    margin-left: -25%;
  }
  .text2{
    color: #fff;
    font-size: 40px;
    font-family: "FC Minimal";
    margin-top: 15%;
    margin-left: 30%;
  }
  .text3{
    color: #BDBDBD;
    font-size: 14px;
  }
  .text4{
    display: inline-block;
    color: #000;
    font-size: 14px;
  }
  .boxin{
    display: block;
    margin-top: 10%;
  }
  .btn2{
    display: inline-block;
    padding: 5px;
    border: 1px solid #000;
    color: #000;
    width: 140px;
    margin-top: 20%;
  }
</style>
