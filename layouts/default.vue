<template>
  <v-app light>
    <v-navigation-drawer v-model="drawer" app>
      <v-list rounded>
        <v-subheader>Категории меню</v-subheader>
        <v-list-item-group color="#B08D4E">
          <v-list-item v-for="c in categories" :key="c.title">
            <v-list-item-avatar>
              <v-img src="https://via.placeholder.com/150" />
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title v-text="c.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app color="#B08D4E">
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <nuxt-link
        tag="img"
        style="cursor: pointer;"
        to="/"
        src="/image/logo.png"
        alt="Naga Bar"
        height="45px"
      />
    </v-app-bar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout justify-center>
          <v-flex>
            <nuxt />
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      categories: [
        { title: 'Суши' },
        { title: 'Ролы' },
        { title: 'Вок' },
        { title: 'Супы' },
        { title: 'Салаты' }
      ]
    }
  }
}
</script>
