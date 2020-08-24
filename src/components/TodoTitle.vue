<template>
  <div class="title">
    <p class="title__message">{{ message }}</p>
    <p class="title__task">
      <span class="title__task-top">You've got</span>
      <span class="title__task-count">
        <em class="title__task-left">{{ propsdata.left }}</em>
        <em v-if="propsdata.total" class="title__task-total">
          / {{ propsdata.total }}</em
        >
      </span>
      <span class="title__task-bottom"> tasks today.</span>
      <span class="title__task-info"></span>
    </p>
  </div>
</template>

<script>
export default {
  props: ["propsdata"],
  data: () => ({
    message: "Hello, nana.",
  }),
  computed: {
    checkCount() {
      const checkLeftItems = () => {
        let leftCount = 0;
        for (let i = 0; i < this.todoItems.length; i++) {
          if (this.todoItems[i].completed === false) {
            leftCount++;
          }
        }
        return leftCount;
      };

      const count = {
        total: this.todoItems.length,
        left: checkLeftItems(),
      };
      return count;
    },
  },
};
</script>
