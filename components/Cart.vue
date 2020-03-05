<template>
  <v-btn text class="pl-4 pr-4" nuxt to="/cart" height="100%">
    <v-badge left color="#303030">
      <span slot="badge">{{ numItems }}</span>
      <v-icon color="lighten-1">mdi-cart</v-icon>
    </v-badge>
    <span>{{ value }} ₽</span>
  </v-btn>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters({
      cart: 'cart/cartItems',
      value: 'cart/cartValue'
    }),
    numItems() {
      return this.cart.reduce((total, item) => {
        total += item.quantity
        return +total
      }, 0)
    }
  },
  methods: {}
}
</script>
