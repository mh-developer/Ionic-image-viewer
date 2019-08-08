<template>
  <div>
    <ion-header>
      <ion-toolbar color="dark">
        <ion-buttons slot="start">
          <ion-button @click="closeModal()">
            <ion-icon slot="icon-only" name="close"></ion-icon>
          </ion-button>
        </ion-buttons>
        <ion-title>{{ imgTitle }}</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content forceOverscroll="false" color="dark" fullscreen="true">
      <ion-slides :options="slideOpts">
        <ion-slide>
          <div class="swiper-zoom-container">
            <img :src="imgSource" height="100vh" />
          </div>
        </ion-slide>
      </ion-slides>
    </ion-content>

    <ion-footer :v-if="imgDescription.length">
      <ion-toolbar color="dark" text-center>
        <ion-text>{{ imgDescription }}</ion-text>
      </ion-toolbar>
    </ion-footer>
  </div>
</template>

<script>
/* eslint-disable */

export default {
  props: {
    imgSource: String,
    imgTitle: String,
    imgDescription: String
  },
  data() {
    return {
      slideOpts: {
        centeredSlides: "true"
      }
    };
  },
  methods: {
    closeModal() {
      this.$ionic.modalController.dismiss();
    }
  }
};
</script>

<style >
ion-slides {
  height: 100%;
}
</style>

