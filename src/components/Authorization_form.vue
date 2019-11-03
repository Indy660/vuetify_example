<template>
  <v-app id="inspire">
    <v-content>
      <v-container
              class="fill-height"
              fluid
      >
        <v-row
                align="center"
                justify="center"
        >
          <v-col
                  cols="12"
                  sm="8"
                  md="4"
          >
            <v-card class="elevation-12">
              <v-toolbar
                      color="primary"
                      dark
                      flat
              >
                <v-toolbar-title>Заполните поля ввода</v-toolbar-title>
              </v-toolbar>
              <v-card-text>
                <v-form>
                  <v-text-field
                          v-model="enterLoginUser"
                          label="Ваш логин"
                          name="login"
                          type="text"
                  />

                  <v-text-field
                          v-model="enterPasswordUser"
                          id="password"
                          label="Ваш пароль"
                          name="password"
                          type="password"
                  />
                </v-form>
              </v-card-text>
              <v-card-actions>
                <v-spacer />
                <v-btn color="primary" v-on:click="checkUser">Войти</v-btn>
              </v-card-actions>
            </v-card>

            <v-alert
                    :value = Boolean(messageWithMistake)
                    type="error"

                   >
              {{messageWithMistake}}
            </v-alert>

          </v-col>
        </v-row>
        <p></p>
      </v-container>
    </v-content>
  </v-app>




</template>

<script>
  export default {
    name: "authorization_form",
    props: ["checkUserFunc", "messageWithMistake"],
    data() {
      return {
        enterLoginUser: null,
        enterPasswordUser: null,

      }
    },
    methods: {
      checkUser: function () {
        this.checkUserFunc(this.enterLoginUser, this.enterPasswordUser);
        this.enterLoginUser = "";
        this.enterPasswordUser = "";
      },

    }
  }
</script>
