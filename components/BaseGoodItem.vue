<template>
  <v-flex xs12 xl3 sm6 md4>
    <v-card>
      <v-img :src="image" class="align-end" height="200px" />
      <v-card-title>{{ title }}</v-card-title>
      <v-card-subtitle class="pb-0">{{ price }}₽</v-card-subtitle>
      <v-card-actions class="pa-5">
        <nuxt-link :to="`goods/${id}`" tag="div">
          <v-btn text="">Подробнее</v-btn>
        </nuxt-link>
        <v-spacer></v-spacer>
        <v-btn fab color="#B08D4E" dark>
          <v-icon @click="addToCart()" dark>mdi-plus</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
import { mapActions } from 'vuex'
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    id: { type: Number, required: true },
    price: { type: Number, required: true },
    image: { type: String, default: '' },
    isDiscount: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    ...mapActions({
      updateCart: 'cart/updateCart'
    }),
    addToCart() {
      const order = {
        item: Object.assign(
          {},
          {
            id: this.id,
            price: this.price,
            title: this.title
          }
        ),
        quantity: 1,
        isAdd: true
      }
      this.updateCart(order)
    }
  }
}
</script>
