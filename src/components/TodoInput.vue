<template>
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12">
          <v-text-field
            v-model="message"
            append-outer-icon="mdi-arrow-right"
            filled
            clear-icon="mdi-close-circle"
            clearable
            label="Enter your task"
            type="text"
            @click:append-outer="sendMessage"
            @click:clear="clearMessage"
          ></v-text-field>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
export default {
  data: () => ({
    password: "Password",
    show: false,
    message: "",
    marker: true,
  }),

  methods: {
    sendMessage() {
      this.clearMessage();
    },
    clearMessage() {
      this.message = "";
    },
  },
};
</script>

<style></style>
