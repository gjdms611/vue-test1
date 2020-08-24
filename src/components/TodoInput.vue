<!-- TodoInput.vue -->

<template>
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12">
          <v-text-field
            v-model="newTodoItem"
            @keyup.enter="addTodoItem"
            append-outer-icon="mdi-arrow-right"
            filled
            clear-icon="mdi-close-circle"
            clearable
            label="Enter your task"
            type="text"
            @click:append-outer="addTodoItem"
            @click:clear="clearTodoItem"
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
    newTodoItem: "",
    marker: true,
  }),

  methods: {
    addTodoItem() {
      if (this.newTodoItem !== "") {
        this.$emit("addItem", this.newTodoItem);
        this.clearTodoItem();
      }
    },
    clearTodoItem() {
      this.newTodoItem = "";
    },
  },
};
</script>

<style></style>
