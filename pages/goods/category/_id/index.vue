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
      goods: [
        // { id: 1, title: 'Ролл с лососем', price: 500, image: 'products/1.JPG' },
        // {
        //   id: 2,
        //   title: 'Ролл Калифорния',
        //   price: 320,
        //   image: 'products/2.JPG'
        // },
        // { id: 3, title: 'Вок с курицей', price: 290, image: 'products/3.JPG' },
        // { id: 4, title: 'Вок с рыбой', price: 290, image: 'products/4.JPG' },
        // {
        //   id: 5,
        //   title: 'Вок со свининой',
        //   price: 290,
        //   image: 'products/5.JPG'
        // },
        // { id: 6, title: 'Рис отварной', price: 190, image: 'products/6.JPG' }
      ]
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
