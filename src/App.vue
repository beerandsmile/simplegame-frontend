<template>
  <v-app dark>
      <v-content>
        Сев не хуй соси
      <HelloWorld/>
      <Login/>
    </v-content>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Login from './components/Login'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Login
  },
  data () {
    return {
      //
    }
  }
}
</script>
