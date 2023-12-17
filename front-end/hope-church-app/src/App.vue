<template>
  <v-app>
    <Signup />
    <v-footer>
      <DefaultFooter />
    </v-footer>
  </v-app>
</template>

<script>
import Signup from './page/signup.vue'
import DefaultFooter from './components/layout/footer/default-footer.vue'

export default {
  name: 'App',
  components: {
    DefaultFooter,
    Signup
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
