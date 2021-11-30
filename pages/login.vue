<template>
  <div class="loginbox">
    <p class="text-center text2">
      HomeRooM
    </p>
    <p class="text-center text3">
      Chaiyaphum Technical College
    </p>
    <div class="boxin text-center">
      <v-form>
        <v-text-field label="Name" outlined />
        <v-text-field label="Password" outlined style="margin-top: -5%;" />
        <v-checkbox label="checkbox" style="margin-top: -10%;" />
        <v-btn outlined class="btn2">
          Log In
        </v-btn>
        <a href="signup">
          <p class="text4">
            Sign up
          </p>
        </a>
      </v-form>
    </div>
  </div>
</template>

<style>
  .loginbox{
    display: block;
    background-color: #fff;
    color: #212121;
    width: 320px;
    height: 500px;
    padding: 20px;
    border-radius: 20px;
    margin: auto;
    margin-top: 10%;
  }
  .text2{
    font-size: 34px;
    line-height : 0;
    margin-top: 15%;
  }
  .text3{
    color: #BDBDBD;
    font-size: 14px;
  }
  .text4{
    color: #FFC107;
    font-size: 14px;
    margin-top: 5%;
  }
  .boxin{
    display: block;
    padding: 35px;
    margin-top: -5%;
  }
  .btn2{
    width: 100px;
    margin-top: 30%;
  }
</style>
