<template>
  <div>
  <h1>Carte des anciens élèves</h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, 
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum 
    dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
  <div class = "map">
    <l-map ref="map" v-model:zoom="data.zoom" :center="[43.6, 1.44]">
      <l-tile-layer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
        layer-type="base"
        name="OpenStreetMap"></l-tile-layer>
      <l-geo-json :geojson="data.geojsondata" ref="geojson" @click="onGeoJsonClick"></l-geo-json>
    </l-map>
  </div>
</div>
</template>

<script setup>
import jsonData from '@/assets/data/sigma_points_emplois.json';
import { LGeoJson, LMap, LTileLayer } from "@vue-leaflet/vue-leaflet";
import "leaflet/dist/leaflet.css";
import { onMounted, reactive } from 'vue';

const data = reactive({map: null, geojsondata: null,zoom:2}); 
/*
const map = ref(null);
const geojsondata = ref(null);
const zoom = ref(2);
*/
const onGeoJsonClick = (event) => {
  console.log('Entité GeoJSON cliquée :', event.layer.feature.properties.nom);
};

onMounted(() => {

  // Initialisation de la carte
  data.map = LMap.value;
  data.geojsondata = jsonData;
});

</script>

<style>

.map{
  height:600px;
  width:auto;
}

</style>
