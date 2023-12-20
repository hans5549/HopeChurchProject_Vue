<template>
    <v-main>
      <v-card class="mx-auto mt-12" width="600">
        <br />
        <h2 class="text-center">註冊一個帳號</h2>
        <br />
        <v-sheet width="450" class="pa-6 mx-auto">
          <v-form>
            <v-text-field
              :rules="[rules.accountRequired]"
              prepend-inner-icon="mdi-account" label="帳號"
              variant="outlined"
              hint="請輸入真實姓名"></v-text-field>
            <br />
            <v-text-field
              :rules="[rules.mailRequired]"
              prepend-inner-icon="mdi-email" label="Email"
              variant="outlined"
              hint="用來寄送忘記密碼確認信"></v-text-field>
            <br />
            <v-text-field :append-inner-icon="loginPasswordVisible ? 'mdi-eye' : 'mdi-eye-off'"
              :type="loginPasswordVisible ? 'text' : 'password'" prepend-inner-icon="mdi-lock-outline" label="密碼"
              variant="outlined" @click:append-inner="loginPasswordVisible = !loginPasswordVisible"></v-text-field>
            <v-btn type="submit" block class="mt-2" color="blue-darken-3">註冊</v-btn>
          </v-form>
          <br />
        </v-sheet>
      </v-card>
    </v-main>
  </template>

  <script>
  export default {
    name: 'LoginSignup',
    data: () => ({
      rules: {
        accountRequired: value => !!value || '此欄位為必填',
        mailRequired: value => !!value || '此欄位為必填',
      },
      loginPasswordVisible: false,
      signupPasswordVisible: false
    })
  }
  </script>
