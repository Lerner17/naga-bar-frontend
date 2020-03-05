<template>
  <div>
    <v-data-table
      :headers="headers"
      :items="cartItems"
      no-data-text="Корзина пустая"
      hide-actions
    >
    </v-data-table>
  </div>
</template>
