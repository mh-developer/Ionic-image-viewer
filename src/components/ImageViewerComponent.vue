<template>
  <div>
    <ion-header>
      <ion-toolbar color="dark">
        <ion-buttons slot="start">
          <ion-button @click="closeModal()">
            <ion-icon slot="icon-only" name="close"></ion-icon>
          </ion-button>
        </ion-buttons>
        <ion-title v-model="setImgTitle">{{ setImgTitle }}</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content forceOverscroll="false" color="dark" fullscreen="true">
      <ion-slides
        ref="slider"
        pager="true"
        @ionSlidesDidLoad="ionSlidesDidLoad()"
        @ionSlideDidChange="ionSlideDidChange()"
      >
        <ion-slide v-for="camera in cameras" :key="camera.imgSource">
          <div class="swiper-zoom-container">
            <img :src="camera.imgSource" height="100vh" />
          </div>
        </ion-slide>
      </ion-slides>
    </ion-content>

    <ion-footer :v-if="setImgDescription.length">
      <ion-toolbar color="dark" text-center>
        <ion-text v-model="setImgDescription">{{ setImgDescription.imgDescription }}</ion-text>
      </ion-toolbar>
    </ion-footer>
  </div>
</template>

<script>
/* eslint-disable */

export default {
  props: {
    cameras: Array,
    index: Number
  },
  methods: {
    ionSlidesDidLoad() {
      let instanceSwiper = this.$refs.slider.swiper;
      instanceSwiper.params.initialSlide = this.index;
      instanceSwiper.params.zoom.maxRatio = 5;
      instanceSwiper.activeIndex = this.index;
      instanceSwiper.slideTo(this.index);
    },
    ionSlideDidChange(event) {
      this.index = this.$refs.slider.swiper.activeIndex;
      this.setImgTitle;
      this.setImgDescription;
    },
    closeModal() {
      this.$ionic.modalController.dismiss();
    }
  },
  computed: {
    setImgTitle() {
      return this.cameras[this.index].imgTitle;
    },
    setImgDescription() {
      let ins = this.cameras[this.index];
      return {
        imgDescription: ins.imgDescription,
        length: ins.imgDescription.length
      };
    }
  }
};
</script>

<style>
ion-slides {
  height: 100%;
}
</style>

