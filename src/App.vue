<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import { ref } from "vue";

const coords = ref([7.812653, 51.682774]);
const projection = ref("EPSG:4326");
const zoom = ref(0);
const _rotation = ref(Math.PI / 2);
</script>

<template>
  <header>
    <div class="logos">
      <img alt="Vue logo" src="./assets/logo.svg" width="125" height="125" />
      <span>+</span>
      <img
        alt="OpenLayers Logo"
        src="./assets/OpenLayers_logo.svg"
        width="125"
        height="125"
        class="logo" />
    </div>

    <div class="wrapper">
      <HelloWorld msg="Vue3 + OpenLayers Example" />
    </div>
  </header>

  <main>
    <ol-map
      :loadTilesWhileAnimating="true"
      :loadTilesWhileInteracting="true"
      style="height: 400px">
      <ol-view
        ref="view"
        :center="coords"
        :rotation="false"
        :zoom="zoom"
        :projection="projection"
        :resolution="0.001" />

      <ol-tile-layer>
        <ol-source-osm />
        <ol-scaleline-control />
      </ol-tile-layer>

      <ol-overlay :position="[7.812653, 51.682774]" :key="item">
        <div
          style="
            background-color: black;
            color: white;
            padding: 2px;
            border-radius: 5px;
          ">
          Hamm
        </div>
      </ol-overlay>
    </ol-map>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logos {
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: bold;
  font-size: 3rem;
  margin-bottom: 1rem;
}

.logo {
  margin-left: 1.2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
