<!-- Tuto réalisé à partir du site : //https://leafletjs.com/ -->
<script setup>
// Import du fichier leaflet.css permettant le bon affichage de la carte
import 'leaflet/dist/leaflet.css';
// Import du hook onMounted pour charger la carte lorsque le composant Vue est monté
import { onMounted } from 'vue';
// Import de la bibliothèque Leaflet installée dans node_modules (via package.json)
// Leaflet est accessible via 'L'
import L from 'leaflet';

onMounted(() => {
  // Création d'une carte Leaflet dont relié à l'id html 'my_map' qui a comme coordonnées GPS [39.75,-105] avec un zoom de 12
  
  const map = L.map('my_map').setView([39.75,-105], 12);

  // données geoJson directement (Très mauvaise pratique)
  const geoJsonData = {
    "type": "Feature",
    "properties": {
        "title": "données geojson",
        "subtitle": "Hello World"
    },
    "geometry": {
        "type": "Point",
        "coordinates": [-104.99404, 39.75621]
    }
};

  //Ajout de la couche open street map via une couche de tuile (tileLayer)
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors'
  }).addTo(map);

  //Ajout d'un geojson avec (https://leafletjs.com/examples/geojson/) 
  L.geoJSON(geoJsonData).addTo(map);
  
  // ajout d'un marker et connexion d'une popup 
  L.marker([39.75,-105]).addTo(map).bindPopup(`<span>Ceci est une popup sur un marker</span><br><span>C'est fou non ?</span>`);
  L.marker([39.77,-105]).addTo(map);
  
});
</script>

<template>
  <div>
    <!-- titre -->
    <h1>Tuto Leaflet</h1>
    <div>
      <!-- div avec l'id my_map dont la taille a été fixé (prérequis leaflet) -->
      <div id="my_map" class="mapleaflet"></div>
    </div>
</div>
</template>

<style scoped>
.mapleaflet{
  height: 400px;
}
</style>
