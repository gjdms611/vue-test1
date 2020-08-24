<template>
  <div>
    <v-card class="mx-auto" max-width="344" outlined>
      <v-list-item two-line class="list">
        <v-list-item-content
          class="list__item"
          v-for="(todoItem, index) in propsdata"
          :key="todoItem.item"
        >
          <v-checkbox
            type="checkbox"
            :id="todoItem.item"
            :checked="todoItem.completed === true"
            @change="toggleComplete(todoItem)"
          />
          <label :for="todoItem.item" class="list__label">
            <p class="list__text">{{ todoItem.item }}</p>
          </label>
          <p class="list__date">{{ todoItem.date }}</p>
          <v-btn
            class="list__delete"
            Delete
            @click="removeTodo(todoItem, index)"
          >
            <div class="blind">Delete</div>
          </v-btn>
        </v-list-item-content>
      </v-list-item>
    </v-card>
  </div>
</template>

<script>
export default {
  props: ["propsdata"],
  data: () => ({
    //
  }),
  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== "loglevel:webpack-dev-server") {
          this.todoItems.push(
            JSON.parse(localStorage.getItem(localStorage.key(i)))
          );
        }
      }
    }
  },
  methods: {
    toggleComplete(todoItem) {
      this.$emit("toggleItem", todoItem);
    },
    removeTodo(todoItem, index) {
      this.$emit("removeItem", todoItem, index);
    }
  }
};
</script>
