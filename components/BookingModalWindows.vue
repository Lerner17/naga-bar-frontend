<template>
  <v-dialog v-model="dialog" persistent max-width="600px">
    <template v-slot:activator="{ on }">
      <v-btn v-on="on" height="100%" text>
        Заказать еду
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        <span class="headline">Заказать еду</span>
      </v-card-title>
      <v-card-text>
        <v-container grid-list-md>
          <v-form ref="form" v-model="valid" validation>
            <p>
              Для оформления заказа позвоните по номеру:
              <a href="tel: +7 991 304 82 72">+7 991 304 82 72</a>,
              <a href="tel: +7 495 19 77677">+7 495 19 77677</a>
            </p>
          </v-form>
        </v-container>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn @click="dialog = false" text>Закрыть</v-btn>
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
