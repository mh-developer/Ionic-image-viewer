<template>
  <div id="app">
    <ion-app>
      <ion-header>
        <ion-toolbar color="primary">
          <ion-title>Ionic Image Zooming</ion-title>
          <!-- <router-link to="/">Home</router-link>|
          <router-link to="/about">About</router-link>-->
        </ion-toolbar>
      </ion-header>
      <ion-content padding>
        <router-view />
      </ion-content>
    </ion-app>
  </div>
</template>

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
