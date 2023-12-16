<template>
  <v-main>
    <v-card class="mx-auto mt-12" width="600">
      <br />
      <h2 class="text-center">主希望光教會</h2>
      <br />
      <v-sheet width="450" class="pa-6 mx-auto">
        <v-form>
          <v-text-field
            prepend-inner-icon="mdi-account"
            label="帳號 (姓名) 或 Email" variant="outlined"></v-text-field>
          <v-text-field
            :append-inner-icon="loginPasswordVisible ? 'mdi-eye' : 'mdi-eye-off'"
            :type="loginPasswordVisible ? 'text' : 'password'"
            prepend-inner-icon="mdi-lock-outline"
            label="密碼" variant="outlined"
            @click:append-inner="loginPasswordVisible = !loginPasswordVisible"></v-text-field>

          <v-dialog width="500">
            <template v-slot:activator="{ props }">
              <v-btn v-bind="props" variant="plain">忘記密碼？</v-btn>
            </template>

            <template v-slot:default="{ isActive }">
              <v-card title="忘記密碼？">
                <v-card-text>
                  <v-container>
                    <v-row>
                      <v-col cols="12">
                        <v-text-field label="Email" variant="outlined"></v-text-field>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-card-text>
                <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn block color="blue-darken-3" @click="isActive.value = false">送出</v-btn>
                </v-card-actions>
              </v-card>
            </template>
          </v-dialog>

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
        <v-row wrap no-gutters>
          <v-col cols="6" class="text-center">
            <v-dialog width="500">
              <template v-slot:activator="{ props }">
                <v-btn v-bind="props" block class="mt-2" color="deep-orange-lighten-1">CGM 帳號登入</v-btn>
              </template>

              <template v-slot:default="{ isActive }">
                <v-card title="CGM Taiwan 帳號認證服務">
                  <v-card-text>
                    <v-container>
                      <v-row>
                        <v-col cols="12">
                          <v-text-field
                            prepend-inner-icon="mdi-account"
                            label="帳號" variant="underlined"></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <v-text-field
                            :append-inner-icon="signupPasswordVisible ? 'mdi-eye' : 'mdi-eye-off'"
                            :type="signupPasswordVisible ? 'text' : 'password'"
                            prepend-inner-icon="mdi-lock"
                            label="密碼" variant="underlined"
                            @click:append-inner="signupPasswordVisible = !signupPasswordVisible"></v-text-field>
                        </v-col>
                      </v-row>
                    </v-container>
                  </v-card-text>
                  <v-card-actions>
                    <v-row wrap no-gutters>
                      <v-col cols="6">
                        <v-btn block color="red-darken-3" @click="isActive.value = false">取消</v-btn>
                      </v-col>
                      <v-col cols="6">
                        <v-btn block class="mt-2" color="blue-darken-3" @click="isActive.value = false">登入</v-btn>
                      </v-col>
                    </v-row>
                  </v-card-actions>
                </v-card>
              </template>
            </v-dialog>
          </v-col>
          <v-spacer></v-spacer>
          <v-col cols="4" class="text-center">
            <v-dialog width="500">
              <template v-slot:activator="{ props }">
                <v-btn v-bind="props" block class="mt-2" color="blue-grey-lighten-4">註冊</v-btn>
              </template>

              <template v-slot:default="{ isActive }">
                <v-card title="註冊">
                  <v-card-text>
                    <v-container>
                      <v-row>
                        <v-col cols="12">
                          <v-text-field
                            prepend-inner-icon="mdi-account"
                            label="姓名" variant="underlined"></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <v-text-field
                            prepend-inner-icon="mdi-mail"
                            label="Email" variant="underlined"></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <v-text-field
                            :append-inner-icon="signupPasswordVisible ? 'mdi-eye' : 'mdi-eye-off'"
                            :type="signupPasswordVisible ? 'text' : 'password'"
                            prepend-inner-icon="mdi-lock"
                            label="密碼" variant="underlined"
                            @click:append-inner="signupPasswordVisible = !signupPasswordVisible"></v-text-field>
                        </v-col>
                      </v-row>
                    </v-container>
                  </v-card-text>
                  <v-card-actions>
                    <v-row wrap no-gutters>
                      <v-col cols="6">
                        <v-btn block color="red-darken-3" @click="isActive.value = false">取消</v-btn>
                      </v-col>
                      <v-col cols="6">
                        <v-btn block class="mt-2" color="blue-darken-3" @click="isActive.value = false">註冊</v-btn>
                      </v-col>
                    </v-row>
                  </v-card-actions>
                </v-card>
              </template>
            </v-dialog>
          </v-col>
        </v-row>
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
