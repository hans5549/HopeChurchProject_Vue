<template>
  <v-main>
    <v-card class="mx-auto mt-12" width="600">
      <br />
      <h2 class="text-center">CGM 帳號登入</h2>
      <br />
      <v-sheet width="450" class="pa-6 mx-auto">
        <v-form>
          <v-text-field prepend-inner-icon="mdi-account" label="帳號" variant="outlined"></v-text-field>
          <v-text-field :append-inner-icon="loginPasswordVisible ? 'mdi-eye' : 'mdi-eye-off'"
            :type="loginPasswordVisible ? 'text' : 'password'" prepend-inner-icon="mdi-lock-outline" label="密碼"
            variant="outlined" @click:append-inner="loginPasswordVisible = !loginPasswordVisible"></v-text-field>
          <v-btn type="submit" block class="mt-2" color="blue-darken-3">登入</v-btn>
        </v-form>
        <br />
        <v-row wrap no-gutters>
          <v-col cols="5" class="text-center">
            <v-divider class="mt-3" />
          </v-col>
          <v-col cols="2" class="text-center text-h6">
            或
          </v-col>
          <v-col cols="5" class="text-center">
            <v-divider class="mt-3" />
          </v-col>
        </v-row>
        <v-btn type="submit" block class="mt-2" color="deep-orange-lighten-1">教會帳號登入</v-btn>
      </v-sheet>
    </v-card>
  </v-main>
</template>

<script>
export default {
  name: 'LoginSignup',
  data: () => ({
    loginPasswordVisible: false,
    signupPasswordVisible: false
  })
}
</script>
