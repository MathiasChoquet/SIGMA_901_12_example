<template>
  <div>
    <h1>Carte des restaurants sympa</h1>
    <h2>Cliquez que les points pour voir les informations</h2>
    <div>
      <div id="map" style="height: 400px;"></div>
    </div>
</div>
</template>

<script setup>
// Importez les styles CSS de Leaflet
import 'leaflet/dist/leaflet.css';
import { onMounted } from 'vue';
// Importez la bibliothèque Leaflet
import L from 'leaflet';

onMounted(() => {
  // Créez une carte Leaflet
  const map = L.map('map').setView([43.57, 1.40], 15);

  // Ajoutez une couche de tuiles (par exemple, OpenStreetMap)
  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap contributors'
  }).addTo(map);

  // Ajoutez un marqueur
  L.marker([43.57, 1.40]).addTo(map).bindPopup(`<span>Restaurants de poisson</span><br><span>Pas cher et bon</span><br><span>Ticket moyen 8€</span>`);
  L.marker([43.566, 1.405]).addTo(map).bindPopup(`<span>Restaurants de viande</span><br><span>cher et pas bon</span><br><span>Ticket moyen 25€</span>`);
});

</script>

<style></style>
