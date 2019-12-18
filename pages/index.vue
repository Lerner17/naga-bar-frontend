<template>
  <v-container grid-list-lg>
    <v-layout raw wrap>
      <BaseGoodItem
        v-for="g in goods"
        :key="g.id"
        :title="g.title"
        :price="g.price"
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
      goods: [
        { id: 1, title: 'Ролл с лососем', price: 500 },
        { id: 2, title: 'Ролл Калифорния', price: 320 },
        { id: 3, title: 'Вок с курицей', price: 290 },
        { id: 4, title: 'Вок с рыбой', price: 290 },
        { id: 5, title: 'Вок со свининой', price: 290 },
        { id: 6, title: 'Рис отварной', price: 190 }
      ]
    }
  }
}
</script>
