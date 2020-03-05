<template>
  <v-app light>
    <v-navigation-drawer v-model="drawer" app>
      <v-list class="hidden-md-and-up">
        <v-subheader>Меню</v-subheader>
        <v-list-item-group class="mb-2">
          <v-list-item
            class="hidden-md-and-up pl-5"
            tag="a"
            href="tel: +7 985 782 45 45"
          >
            <v-list-item-action>
              <v-icon>mdi-phone</v-icon>
            </v-list-item-action>
            <v-list-item-title tag="address">
              +7 985 782 45 45
            </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
      <v-list rounded>
        <v-list-item-group color="#B08D4E" class="hidden-md-and-up">
          <nuxt-link
            v-for="l in links"
            :key="l.title"
            :to="l.link"
            tag="v-list-item"
          >
            <v-list-item-action>
              <v-icon>{{ l.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title v-text="l.title" />
            </v-list-item-content>
          </nuxt-link>
        </v-list-item-group>
      </v-list>
      <v-divider class="hidden-md-and-up"></v-divider>
      <v-list rounded>
        <v-subheader>Категории меню</v-subheader>
        <v-list-item-group color="#B08D4E">
          <v-list-item v-for="c in categories" :key="c.title">
            <v-list-item-avatar>
              <v-img src="/products/1.JPG" />
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
      <address class="hidden-sm-and-down">
        <v-icon class="pr-1">mdi-phone</v-icon>
        <a
          style="text-decoration: none; color: white;"
          href="tel: +7 991 304 82 72"
        >
          +7 991 304 82 72
        </a>
      </address>
      <v-spacer></v-spacer>
      <nuxt-link
        v-for="link in links"
        :key="link.title"
        :to="link.link"
        tag="div"
        style="height: 100%;"
      >
        <v-btn class="hidden-sm-and-down" height="100%" text>
          {{ link.title }}
        </v-btn>
      </nuxt-link>
      <Cart />
    </v-app-bar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout column justify-center>
          <v-flex>
            <nuxt />
          </v-flex>
          <v-flex>
            <v-footer height="300px">
              <img src="/image/logo.png" height="60px" />
            </v-footer>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Cart from '@/components/Cart.vue'
export default {
  components: { Cart },
  data() {
    return {
      drawer: true,
      links: [
        { title: 'Меню', link: '/goods/all', icon: 'mdi-ballot-outline' },
        { title: 'Вход', link: '/auth/login', icon: 'mdi-login-variant' },
        {
          title: 'Регистрация',
          link: '/auth/register',
          icon: 'mdi-account-plus'
        }
      ],
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

<style>
address {
  text-decoration: none;
  padding-left: 20px;
  font-style: normal;
  font-size: 18px;
}
/* 
.v-input--is--focused {

} */
</style>
