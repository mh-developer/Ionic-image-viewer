# vue image zooming

## Project setup
<!-- https://alligator.io/ionic/ionic-4-vue-skeleton-text/ -->
```
npm install -g ionic

npm install -g @vue/cli

npm install

npm install ionicons@^4.5.9-1

ionic init

ionic integrations enable capacitor
ionic capacitor add android
```
<!-- https://capacitor.ionicframework.com/docs/getting-started/with-ionic/ -->

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build

npx cap add android  // če že imaš "/android" ne rabiš izvesti tega ukaza

npx cap sync  ali  npx cap copy

// ukaz odpre Android Studio, kjer lahko zaženeš
// aplikacijo v emulatorju ali narediš APK
npx cap open android
```
<!-- 
ionic capacitor add android
ionic capacitor copy android 
-->

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
