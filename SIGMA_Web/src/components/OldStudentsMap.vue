<template>
  <div>
  <h1>Carte des anciens élèves</h1>
  <div class = "map">
    <l-map ref="map" v-model:zoom="zoom" :center="[43.6, 1.44]">
      <l-tile-layer
        url="https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png"
        layer-type="base"
        name="OpenStreetMap"></l-tile-layer>
      <l-geo-json :geojson="geojsondata" ref="geojson" @click="onGeoJsonClick"></l-geo-json>
    </l-map>
  </div>
</div>
</template>

<script setup>
import jsonData from '@/assets/sigma_points_emplois.json';
import { LGeoJson, LMap, LTileLayer } from "@vue-leaflet/vue-leaflet";
import "leaflet/dist/leaflet.css";
import { onMounted, ref } from 'vue';

const map = ref(null);
const geojsondata = ref(null);
const zoom = ref(2);

const onGeoJsonClick = (event) => {
  console.log('Entité GeoJSON cliquée :', event.layer.feature.properties.nom);
};

onMounted(() => {

  // Initialisation de la carte
  map.value = LMap.value;
  geojsondata.value = jsonData;
});



</script>

<style>

.map{
  height:600px;
  width:auto;
}

</style>
