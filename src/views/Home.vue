<template>
  <div class="home">
    <ion-card>
      <ion-img v-bind:src="imgSource" @click="viewImage(imgSource, imgTitle, imgDescription)"></ion-img>
      <ion-card-content>
        Klikni na sliko, da ti jo odpre, nato pa jo lahko povečuješ z dvema prstoma
      </ion-card-content>
    </ion-card>
  </div>
</template>

<script>
// @ is an alias to /src
/* eslint-disable */
import ImageViewerComponent from "@/components/ImageViewerComponent.vue";

export default {
  name: "home",
  data() {
    return {
      imgSource: "https://via.placeholder.com/500/92c952",
      imgTitle: "Kamera 1",
      imgDescription: "Opis slike (ni obvezen, lahko nastaviš na prazen niz)"
    };
  },
  methods: {
    async viewImage(imgSource, imgTitle, imgDescription) {
      return await this.$ionic.modalController
        .create({
          component: ImageViewerComponent,
          componentProps: {
            propsData: {
              imgSource,
              imgTitle,
              imgDescription
            }
          },
          cssClass: "modal-fullscreen",
          keyboardClose: true,
          showBackdrop: true
        })
        .then(m => m.present());
    }
  }
};
</script>
