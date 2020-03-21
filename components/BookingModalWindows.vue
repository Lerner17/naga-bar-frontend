<template>
  <v-dialog v-model="dialog" persistent max-width="600px">
    <template v-slot:activator="{ on }">
      <v-btn height="100%" text v-on="on">
        <v-icon>mdi-pencil</v-icon>
        Забронировать столик
      </v-btn>
    </template>
    <v-card>
      <v-card-title>
        <span class="headline">Забронировать столик</span>
      </v-card-title>
      <v-card-text>
        <v-container grid-list-md>
          <v-form validation v-model="valid" ref="form">
            <v-layout wrap>
              <v-flex xs12>
                <v-text-field label="Имя" required />
              </v-flex>
              <v-flex xs12>
                <v-text-field label="Телефон" required />
              </v-flex>
              <v-flex xs12 md6>
                <v-text-field label="Количество персон" />
              </v-flex>
              <v-flex xs12 md6>
                <v-text-field label="Время" />
              </v-flex>
              <v-flex>
                <v-textarea label="Комментарий к брони" />
              </v-flex>
            </v-layout>
          </v-form>
        </v-container>
        <small>*обязательные поля</small>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn text @click="dialog = false">Отменить</v-btn>
        <v-btn color="#B08D4E">Забронировать</v-btn>
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
