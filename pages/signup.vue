<template>
  <div class="card1">
    <p>Sign up your bank account</p>
    <div class="card2">
      <v-text-field
        label="Your Name"
        outlined
        dense
        light
      />
      <v-text-field
        label="Bank Account"
        outlined
        dense
        light
      />
      <v-text-field
        label="Mobile phone number"
        outlined
        dense
        light
      />
      <v-text-field
        label="Email"
        outlined
        dense
        light
      />
      <v-text-field
        label="Password"
        outlined
        dense
        light
        append-icon="mdi-eye"
      />
      <p class="text-left" style="margin: -10px 20px 20px;">
        Use 6 characters with a mix of numbers and letters
      </p>
      <v-checkbox
        label="By signing up, you agree to Bank's Term of Use & Privacy Policy."
        light
      />
      <v-row>
        <v-btn class="ma-2 btn2" color="yellow accent-4" elevation="0">
          <span class="txt1">Sign up</span>
        </v-btn>
        <p class="txt2">or</p>
        <v-btn class="ma-2 btn2" outlined color="indigo">
          Cancel
        </v-btn>
      </v-row>
    </div>
    <p class="txt3">Already signed up? Log in</p>
  </div>
</template>

<style>
  .card1{
    background-color: #fff;
    padding: 30px;
    border-radius: 20px;
    color: #5842ff;
    font-size: 12px;
  }
  .card2{
    padding: 10px;
  }
  .txt1{
    color: brown;
  }
  .txt2{
    font-size: 18px;
    color: #424242;
    margin: 10px 10px 10px;
  }
  .txt3{
    font-size: 14px;
    color: #424242;
    margin-top: 10px;
  }
  .btn2{
    width: 105px;
  }
</style>
