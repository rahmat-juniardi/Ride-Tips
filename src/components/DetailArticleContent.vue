<template>
  <div class="article-content">
    <h1 class="banner-title text-start my-md-6 my-3">
      {{ article.judul }}
    </h1>
    <p class="my-3 d-block d-sm-none">Release Tips : {{ article.tanggal }}</p>

    <div class="mb-4">
      <v-img
        class="shadow image-content"
        width="inherit"
        height="500"
        :aspect-ratio="1"
        :src="article.gambar"
        cover
      ></v-img>
    </div>
    <p class="banner-description text-justify" v-html="article.content"></p>
    <share-button :shareSocialMedia="shareSocialMedia" />
  </div>
</template>

<script>
import ShareButton from "@/components/ShareButton.vue";

export default {
  name: "ArticleContent",
  props: ["article"],
  data() {
    return {
      shareSocialMedia: "",
    };
  },
  components: {
    ShareButton,
  },
  mounted() {
    this.shareSocialMedia = window.location.href;
  },
};
</script>

<style>
.detail-content {
  /* border: 1px solid rgb(167, 167, 167); */
  border-radius: 15px;
  /* padding: 30px !important; */

  /* box-shadow: rgba(149, 157, 165, 0.2) 0px 8px 24px; */
}
.image-content {
  border-radius: 15px;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}
.centered-div {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
}
</style>
