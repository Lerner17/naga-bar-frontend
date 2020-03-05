<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar>
            <v-toolbar-title>Вход</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form ref="form" validation>
              <v-text-field
                prepend-icon="mdi-account"
                name="login"
                label="Электронная почта"
                type="email"
              />
              <v-text-field
                id="password"
                prepend-icon="mdi-lock"
                name="password"
                label="Пароль"
                type="password"
              />
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn text nuxt-link="true" to="/auth/register" tag="v-btn">
              Зарегистрироваться
            </v-btn>
            <v-btn color="#ac8f58">Вход</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>
