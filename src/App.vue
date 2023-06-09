<template>
  <v-app app>
    <navbar />
    <v-content class="">
      <router-view></router-view>
    </v-content>
    <app-footer />
  </v-app>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import AppFooter from "@/components/AppFooter.vue";

export default {
  el: "#app",
  data() {
    return {};
  },
  components: {
    Navbar,
    AppFooter,
  },
};
</script>

<style></style>
