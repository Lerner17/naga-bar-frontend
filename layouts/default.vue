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
          <nuxt-link
            tag="v-list-item"
            v-for="c in categories"
            :key="c.title"
            :to="`/goods/category/${c.id}`"
          >
            <v-list-item-avatar>
              <v-img v-if="c.image" :src="c.image" />
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-title v-text="c.title" />
            </v-list-item-content>
          </nuxt-link>
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
      <BookingModalWindows />
      <nuxt-link
        v-for="link in links"
        :key="link.title"
        :to="link.link"
        tag="div"
        style="height: 45px"
      >
        <v-btn class="hidden-sm-and-down" height="100%" text>
          {{ link.title }}
        </v-btn>
      </nuxt-link>
    </v-app-bar>
    <v-content>
      <v-container fluid fill-height>
        <v-layout column justify-center>
          <v-flex>
            <nuxt />
          </v-flex>
          <v-flex>
            <v-footer>
              <v-layout column>
                <v-flex>
                  <address class="pt-1">
                    <v-icon class="pr-1">mdi-map-marker</v-icon>
                    Земляной вал 14/16 стр 1
                  </address>
                </v-flex>
                <v-flex>
                  <v-icon>mdi-phone</v-icon>
                  +7 888 88 11 11
                </v-flex>
              </v-layout>
              <v-label>
                <v-flex>
                  <v-btn href="https://www.instagram.com/naga.bar/">
                    <v-icon>mdi-instagram</v-icon>
                  </v-btn>
                </v-flex>
              </v-label>
            </v-footer>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import BookingModalWindows from '../components/BookingModalWindows'
export default {
  components: { BookingModalWindows },
  data() {
    return {
      drawer: true,
      dialog: false,
      links: [
        // {
        //   title: 'Забронировать столик',
        //   link: '/goods/all',
        //   icon: 'mdi-pencil'
        // }
        // { title: 'Вход', link: '/auth/login', icon: 'mdi-login-variant' },
        // {
        //   title: 'Регистрация',
        //   link: '/auth/register',
        //   icon: 'mdi-account-plus'
        // }
      ],
      categories: []
    }
  },
  mounted() {
    this.$axios.$get('https://naga.bar/api/v1/goods-category/').then((data) => {
      this.categories = data
    })
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
