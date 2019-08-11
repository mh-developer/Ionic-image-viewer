<template>
  <div id="app">
    <ion-app>
      <ion-header>
        <ion-toolbar color="primary">
          <ion-title>Video nadzorni sistem</ion-title>
          <!-- <router-link to="/">Home</router-link>|
          <router-link to="/about">About</router-link>-->
        </ion-toolbar>
      </ion-header>
      <ion-content padding>
        <ion-refresher slot="fixed" @ionRefresh="doRefresh($event)">
          <ion-refresher-content></ion-refresher-content>
        </ion-refresher>

        <router-view v-if="isRouterAlive" />
      </ion-content>
    </ion-app>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  data() {
    return {
      isRouterAlive: true
    };
  },
  methods: {
    doRefresh(event) {
      this.isRouterAlive = false

      setTimeout(() => {
        this.isRouterAlive = true
        event.target.complete();
      }, 500);
    }
  }
};
</script>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.modal-fullscreen .modal-wrapper {
  position: absolute;
  top: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 100%;
}
</style>
