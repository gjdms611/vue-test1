<template>
  <div>
    <v-app-bar color="white">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>My ToDo</v-toolbar-title>

      <v-spacer></v-spacer>

      <p class="date">{{ timestamp }}</p>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      timestamp: "",
    };
  },
  created() {
    const now = new Date();
    const month = now.getMonth() + 1;
    const date = now.getDate();
    const weekList = new Array(
      "Sun.",
      "Mon.",
      "Tue.",
      "Wed.",
      "Thu.",
      "Fri.",
      "Sat."
    );
    const week = weekList[now.getDay()];
    this.timestamp = `${month}/${date} ${week}`;
  },
};
</script>
