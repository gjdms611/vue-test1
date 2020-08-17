<template>
  <div>
    <v-card class="mx-auto" max-width="344" outlined>
      <v-container fluid>
        <v-row class="card--list">
          <v-col cols="4">
            <v-checkbox v-model="checkbox1" :label="`Smile! :)`"></v-checkbox
          ></v-col>
          <v-col cols="4"
            ><v-card-text>5/26</v-card-text><v-button>x</v-button></v-col
          >
        </v-row>
      </v-container>
    </v-card>

    <ul class="list">
      <li class="list__item">
        <input type="checkbox" id="list-item-1" />
        <label for="list-item-1">
          <p class="list__text">Smile! :)</p>
        </label>
        <p class="list__date">5/26</p>
        <button class="list__delete">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      checkbox1: true,
      checkbox2: false,
    };
  },
};
</script>

<style></style>
