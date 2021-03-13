<template>
  <div>
    <!-- aaaaaaa -->
    <!-- <v-input></v-input> -->
    <!-- <div>{{ texts }}</div> -->
    <div v-for="text in texts" :key="text">
      <v-card color="#385F73" dark>
        <v-card-title class="headline"> {{ text }} </v-card-title>

        <!-- <v-card-subtitle
          >Listen to your favorite artists and albums whenever and wherever,
          online and offline.</v-card-subtitle
        > -->

        <!-- <v-card-actions>
          <v-btn text> Listen Now </v-btn>
        </v-card-actions> -->
      </v-card>
      <!-- {{ text }} -->
    </div>

    <!-- <div>{{ message }}</div> -->
    <!-- <v-text-field
      v-model="message"
      label="Message"
      hide-details="auto"
    ></v-text-field> -->
    <!-- <v-form> -->
    <v-footer app color="transparent" height="72" inset>
      <v-text-field
        v-model="message"
        :append-outer-icon="message ? 'mdi-send' : 'mdi-send'"
        filled
        clear-icon="mdi-close-circle"
        clearable
        label="Message"
        type="text"
        @click:append-outer="sendMessage"
        @click:clear="clearMessage"
        @keyup.enter="sendMessage()"
      ></v-text-field>
    </v-footer>
    <!-- </v-form> -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      texts: [],
      message: '',
    }
  },

  methods: {
    sendMessage() {
      this.texts.push(this.message)
      this.clearMessage()
    },
    clearMessage() {
      this.message = ''
    },
  },
}
</script>

<style scoped></style>
