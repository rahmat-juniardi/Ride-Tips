<template>
  <v-row>
    <v-col cols="12">
      <v-divider class="my-5"></v-divider>
      <p class="">Share this tips into your Friends</p>
      <v-btn
        text
        class="btn-share"
        target="_blank"
        :href="
          `https://www.facebook.com/sharer/sharer.php?u=` + shareSocialMedia
        "
      >
        <v-icon class="fa fa-facebook" aria-hidden="true"></v-icon>
      </v-btn>
      <v-btn
        text
        class="btn-share"
        target="_blank"
        :href="
          `https://twitter.com/intent/tweet?url=` + shareSocialMedia + `/&text=`
        "
      >
        <v-icon class="fa fa-twitter" aria-hidden="true"></v-icon>
      </v-btn>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: "ShareButton",
  props: ["shareSocialMedia"],
};
</script>

<style></style>
