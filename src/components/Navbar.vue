<template>
  <div class="Navbar">
    <v-app-bar app>
      <v-app-bar-nav-icon
        @click="drawer = true"
        class="d-flex d-sm-none"
      ></v-app-bar-nav-icon>
      <v-toolbar-title class="pr-6 bold" style="width: 250px"
        >Ride Tips</v-toolbar-title
      >
      <v-spacer></v-spacer>

      <!-- Navbar -->
      <v-tabs v-model="tab" align-with-title class="d-none d-sm-flex">
        <v-tabs-slider color="#505050"></v-tabs-slider>
        <v-tab router to="/">Home</v-tab>
        <v-tab router to="/tips">Tips Automotive</v-tab>
      </v-tabs>
    </v-app-bar>
    <!-- End Navbar -->

    <!-- Add a navigation drawer bar -->
    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item router to="/">Home</v-list-item>
          <v-list-item router to="/tips">Tips Automotive</v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <!-- Navigation bar drawer ends -->
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      drawer: false,
      tab: null,
    };
  },
};
</script>

<style>
.theme--light.v-app-bar.v-toolbar.v-sheet {
  background-color: #fff;
}
</style>
