<template>
  <v-container class="pa-0" fluid>
    <!-- Banner -->
    <v-row>
      <v-col cols="12">
        <div class="banner">
          <div class="banner-overlay"></div>
          <div class="banner-image-container">
            <div
              class="banner-image"
              :style="{
                backgroundImage:
                  'url(https://www.nerdwallet.com/assets/blog/wp-content/uploads/2022/06/GettyImages-1343076140.jpg)',
              }"
            ></div>
          </div>
          <div class="banner-content">
            <h1 class="banner-title">
              Making Easier Maintenance Your Automotive By Yourself
            </h1>
            <p class="banner-description my-5">
              Our team of automotive experts has curated a collection of
              insightful articles and guides to help you navigate the
              intricacies of the automotive industry. From maintenance and
              repairs to performance upgrades and car buying advice, we offer a
              wide range of topics to cater to your interests.
            </p>
            <v-btn color="primary" router to="/tips">Let's Get Started</v-btn>
          </div>
        </div>
      </v-col>
    </v-row>

    <v-row class="mx-6 mx-md-12 mx-sm-6 my-5">
      <v-col>
        <h1 class="d-sm-inline">Tips Automotive</h1>
        <v-btn plain class="float-sm-right btn-seeMoreTips" router to="/tips"
          >See More Tips</v-btn
        >
      </v-col>
    </v-row>
    <!-- List Article -->
    <article-row :page="page" />
  </v-container>
</template>

<script>
import ArticleRow from "@/components/ArticleRow.vue";

export default {
  name: "Home",
  data() {
    return {
      page: "Home",
    };
  },
  components: {
    ArticleRow,
  },
};
</script>

<style scoped></style>
