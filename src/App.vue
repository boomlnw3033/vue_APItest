<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <v-app id="inspire">
    <v-app-bar class="px-3" color="#A084DC" flat density="compact">
      <v-avatar color="#EBC7E6" size="32"></v-avatar>

      <v-spacer></v-spacer>

      <v-tabs centered color="grey-darken-2">
        <v-tab>
          <RouterLink to="/product">Product</RouterLink>
        </v-tab>
      </v-tabs>
      <v-spacer></v-spacer>

      <v-avatar class="hidden-sm-and-down" color="#EBC7E6" size="32"></v-avatar>
    </v-app-bar>
    <v-main color="#A084DC"><RouterView /></v-main>
  </v-app>
</template>

<style scoped></style>
