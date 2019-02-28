<template>
  <div>
    <v-form v-model="valid" ref="form">
      <v-container>
        <v-layout>
          <v-flex xs12 md4>
            <v-text-field
              v-model="firstname"
              :rules="nameRules"
              :counter="10"
              label="Логин"
              required
            ></v-text-field>
          </v-flex>

          <v-flex xs12 md4>
            <v-text-field
              v-model="password"
              :append-icon="show1 ? 'visibility_off' : 'visibility'"
              :rules="[rules.required, rules.min]"
              :type="show1 ? 'text' : 'password'"
              name="input-10-1"
              label="Пароль"
              counter
              @click:append="show1 = !show1"
            ></v-text-field>
          </v-flex>
        </v-layout>
      </v-container>
    </v-form>
    <center>
      <v-btn color="green" @click="reg">Penitration</v-btn>
    </center>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show1: false,
      password: "",
      rules: {
        required: value => !!value || "Required.",
        min: v => v.length >= 8 || "Min 8 characters"
      },
      valid: false,
      firstname: "",
      lastname: "",
      nameRules: [
        v => !!v || "Name is required",
        v => v.length <= 10 || "Name must be less than 10 characters"
      ]
    };
  },
  methods: {
    reg: function() {
      if (this.$refs.form.validate()) {
        axios
          .post("http://cluster.terehov.buhojmedved.ru/api/v1/auth/", {
            password: this.password,
            name: this.firstname
          })
          .then(function(response) {
            console.log(response);
          })
          .catch(function(error) {
            console.log(error);
          });
      }
    }
  }
};
</script>

<style>
</style>