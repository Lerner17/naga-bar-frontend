<template>
  <v-dialog v-model="dialog" persistent max-width="600px">
    <template v-slot:activator="{ on }">
      <v-btn height="100%" text v-on="on">
        Заказать еду
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        <span class="headline">Заказать еду</span>
      </v-card-title>
      <v-card-text>
        <v-container grid-list-md>
          <v-form validation v-model="valid" ref="form">
	    <p>
		Для оформления заказа позвоните по номеру: <a href="tel: +7 991 304 82 72">+7 991 304 82 72</a>
	    </p>
	  </v-form>
        </v-container>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn text @click="dialog = false">Закрыть</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: 'BookingModalWindows',
  props: {
    dialog: {
      type: Boolean,
      default: false
    }
  }
}
</script>
