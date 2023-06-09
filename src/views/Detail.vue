<template>
  <v-container>
    <v-row class="justify-center align-center">
      <v-col cols="12" sm="10" md="10" lg="8" class="detail-content my-md-10">
        <div class="inline">
          <v-icon
            class="fa fa-angle-left mb-1"
            aria-hidden="true"
            color="black"
          ></v-icon>

          <v-btn class="inline" plain to="/tips" color="black"
            >Tips Automotive</v-btn
          >
          <p class="mt-1 inline float-right d-none d-sm-block">
            Release Tips : {{ article.tanggal }}
          </p>

          <v-divider></v-divider>
        </div>
        <article-content :article="article" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
import ArticleContent from "@/components/DetailArticleContent.vue";

export default {
  name: "ArticleDetail",
  data() {
    return {
      article: {},
    };
  },
  components: {
    ArticleContent,
  },
  methods: {
    setArticle(data) {
      this.article = data;
    },
  },
  // https://api.npoint.io/e504ca1925edd48a7292
  mounted() {
    axios
      .get(
        "https://api.npoint.io/e504ca1925edd48a7292/articles/" +
          this.$route.params.id
      )
      .then((response) => this.setArticle(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style>
.centered-div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}
</style>
