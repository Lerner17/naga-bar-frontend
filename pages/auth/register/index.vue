<template>
  <v-container fluid fill-height>
    <v-layout align-center justify-center>
      <v-flex xs12 sm8 md4>
        <v-card class="elevation-12">
          <v-toolbar color="#ac8f58">
            <v-toolbar-title>Регистрация</v-toolbar-title>
          </v-toolbar>
          <v-card-text>
            <v-form ref="form" validation>
              <v-text-field
                prepend-icon="mdi-at"
                name="login"
                label="Электронная почта"
                type="email"
              />
              <v-text-field
                prepend-icon="mdi-account"
                name="login"
                label="Имя"
                type="text"
              />
              <v-text-field
                id="password"
                prepend-icon="mdi-lock"
                name="password"
                label="Пароль"
                type="password"
              />
              <v-text-field
                id="password"
                prepend-icon="mdi-lock"
                name="password"
                label="Повторите пароль"
                type="password"
              />
              <v-text-field
                prepend-icon="mdi-phone"
                name="login"
                label="Телефон"
                type="text"
              />
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn :disabled="true" text to="/auth/register" color="#ac8f58">
              Зарегистрироваться
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<style>
.v-input__icon--prepend .v-icon {
  color: #ac8f58;
}
</style>
