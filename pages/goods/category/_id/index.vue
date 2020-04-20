<template>
  <v-container grid-list-lg>
    <v-layout raw wrap>
      <BaseGoodItem
        v-for="g in goods"
        :key="g.id"
        :id="g.id"
        :title="g.title"
        :price="g.price"
        :image="g.image"
      />
    </v-layout>
  </v-container>
</template>

<script>
import BaseGoodItem from '@/components/BaseGoodItem.vue'
export default {
  components: { BaseGoodItem },
  data() {
    return {
      goods: []
    }
  },
  mounted() {
    this.$axios
      .$get('https://naga.bar/api/v1/goods/category/' + this.$route.params.id)
      .then((data) => {
        this.goods = data
      })
  }
}
</script>
