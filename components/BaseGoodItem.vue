<template>
  <v-flex xs12 xl3 sm6 md4>
    <v-card>
      <v-img
        class="align-end"
        height="200px"
        src="https://via.placeholder.com/450x200/"
      />
      <v-card-title>{{ title }}</v-card-title>
      <v-card-subtitle class="pb-0">{{ price }}₽</v-card-subtitle>
      <v-card-actions class="pa-5">
        <v-btn text>Подробнее</v-btn>
        <v-spacer></v-spacer>
        <v-btn fab color="#B08D4E" dark>
          <v-icon dark>mdi-plus</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    price: {
      Number,
      required: true
    },
    isDiscount: {
      type: Boolean,
      default: false
    }
  }
}
</script>
