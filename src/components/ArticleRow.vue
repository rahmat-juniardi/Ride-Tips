<template>
  <div class="list-article">
    <v-row class="mx-2 mx-md-12 mx-sm-6">
      <v-col
        v-for="(article, index) in paginatedArticles"
        :key="index"
        cols="12"
        sm="6"
        md="6"
        lg="3"
      >
        <v-card>
          <v-img :src="article.gambar" aspect-ratio="16/9" height="250" cover>
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular
                  indeterminate
                  color="grey-lighten-5"
                ></v-progress-circular>
              </v-row>
            </template>
          </v-img>
          <v-card-title class="article-title"
            ><h5 class="mb-2" v-html="sliceText(article.judul, 35)"></h5>
          </v-card-title>
          <v-card-subtitle>{{ article.tanggal }}</v-card-subtitle>
          <v-card-text class="pb-0">
            <div v-html="sliceText(article.content, 100)"></div>
          </v-card-text>
          <v-card-actions class="pt-0">
            <v-btn color="primary" router :to="'/detail/' + article.id" text
              >Read More</v-btn
            >
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-pagination
      v-model="currentPage"
      :length="totalPages"
      align="center"
      class="mt-6"
      v-bind:class="paginatedShow"
    ></v-pagination>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "PreviewListArticle",
  props: ["page"],
  data() {
    return {
      articles: [],
      itemsPerPage: 4,
      currentPage: 1,
    };
  },
  computed: {
    paginatedShow: function () {
      return this.page == "Home" ? "d-none" : "";
    },
    paginatedArticles() {
      const startIndex = (this.currentPage - 1) * this.itemsPerPage;
      const endIndex = startIndex + this.itemsPerPage;
      return this.articles.slice(startIndex, endIndex);
    },
    totalPages() {
      return Math.ceil(this.articles.length / this.itemsPerPage);
    },
  },
  methods: {
    formatDate(dateString) {
      const options = { year: "numeric", month: "long", day: "numeric" };
      return new Date(dateString).toLocaleDateString(undefined, options);
    },
    sliceText(text, maxLength) {
      if (text.length <= maxLength) {
        return text;
      }
      return text.slice(0, maxLength) + "...";
    },
    setArticle(data) {
      if (this.page == "Home") {
        this.articles = data.slice(0, 4);
      } else {
        this.articles = data;
      }

      console.log(this.articlesHomePage);
    },
  },
  mounted() {
    axios
      .get("https://api.npoint.io/e504ca1925edd48a7292/articles")
      .then((response) => this.setArticle(response.data))
      .catch((error) => console.log(error));
  },
};
</script>

<style></style>
