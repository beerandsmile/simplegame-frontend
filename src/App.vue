<template>
  <v-app dark>
      <v-content>
            <center>
      <v-btn color="red" @click="reg">Соснуть хуй</v-btn>
    </center>
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
