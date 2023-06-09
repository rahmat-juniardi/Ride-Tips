<template>
  <v-container>
    <v-row class="mx-2 mx-md-12 mx-sm-6 mt-3">
      <v-col>
        <h1 class="my-8">Tips Automotive</h1>
      </v-col>
    </v-row>

    <article-row :page="page" />
  </v-container>
</template>

<script>
import ArticleRow from "@/components/ArticleRow.vue";

// import axios from "axios";

export default {
  name: "ListArticle",
  components: {
    ArticleRow,
  },
  data() {
    return {
      page: "ListArticle",
    };
  },
};
</script>

<style></style>
