<template>
  <v-container>
    <v-layout row justify-center>
      <v-flex sm12 md6>
        <v-card>
          <v-img :src="item.image" class="align-end" height="200px" />
          <v-card-title>
            <v-layout column>
              <v-flex align-self-start>
                <h1>{{ item.title }}</h1>
              </v-flex>
              <v-flex class="pt-4 pl-2">
                <p v-if="item.description">
                  {{ item.description }}
                </p>
                <p v-else>
                  Нет описания
                </p>
              </v-flex>
              <v-flex align-self-start>
                <!-- <v-chip v-for="com in good.composition" :key="com.id">{{ com.title }}</v-chip> -->
              </v-flex>
            </v-layout>
          </v-card-title>
          <!-- <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="#ac8f58">Добавить в корзину</v-btn>
          </v-card-actions> -->
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      item: null
    }
  },
  mounted() {
    this.$axios
      .$get(`https://naga.bar/api/v1/goods/${this.$route.params.id}/`)
      .then((data) => {
        this.item = data
      })
  }
}
</script>
