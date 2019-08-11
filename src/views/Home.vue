<template>
  <div class="home">
    <div v-for="(camera, index) in cameras" :key="camera.imgSource">
      <ion-card>
        <ion-img
          :src="camera.imgSource"
          @click="viewImage(camera.imgSource, camera.imgTitle, camera.imgDescription, index)"
        ></ion-img>
        <ion-card-header>
          <ion-card-subtitle>Kamera</ion-card-subtitle>
          <ion-card-title>{{ camera.imgTitle }}</ion-card-title>
        </ion-card-header>
        <ion-card-content>Klikni na sliko, da ti jo odpre, nato pa jo lahko povečuješ z dvema prstoma</ion-card-content>
      </ion-card>
    </div>
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
      cameras: [
        {
          imgSource: "https://via.placeholder.com/500/92c952",
          imgTitle: "Kamera 1",
          imgDescription:
            "Opis slike (ni obvezen, lahko nastaviš na prazen niz)"
        },
        {
          imgSource: "https://via.placeholder.com/500/32c952",
          imgTitle: "Kamera 2",
          imgDescription:
            "Opis slike (ni obvezen, lahko nastaviš na prazen niz)"
        },
        {
          imgSource: "https://via.placeholder.com/500/62c952",
          imgTitle: "Kamera 3",
          imgDescription:
            "Opis slike (ni obvezen, lahko nastaviš na prazen niz)"
        }
      ]
    };
  },
  methods: {
     viewImage(imgSource, imgTitle, imgDescription, index) {
      return  this.$ionic.modalController
        .create({
          component: ImageViewerComponent,
          componentProps: {
            propsData: {
              cameras: this.cameras,
              index
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
