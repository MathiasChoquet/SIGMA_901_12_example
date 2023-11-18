<script setup>
import OldStudentsMap from './components/OldStudentsMap.vue';
import RestaurantsMap from './components/RestaurantsMap.vue';
import SigmaHeader from './components/SigmaHeader.vue';
</script>

<template>
  <main>
    <SigmaHeader class="generic-component" />
    <OldStudentsMap class="generic-component" id="oldStudentsMap" />
    <RestaurantsMap class="generic-component" id="restaurantsMap" /> 
  </main>
  <footer class="generic-component">Réalisé par les master II de la promotion 2023/2024</footer>
</template>

<style scoped>
</style>
