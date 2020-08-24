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
import getDate from "../assets/commonJS/getDate.js";

export default {
  data: () => ({
    timestamp: ""
  }),
  created() {
    this.timestamp = `${getDate().month}/${getDate().date} ${getDate().week}`;
  }
};
</script>
