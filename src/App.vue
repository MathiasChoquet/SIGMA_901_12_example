<script setup>
import json from '@/assets/data/App.json';
import LeafletTutorial from './components/LeafletTutorial.vue';
import OldStudentsMap from './components/OldStudentsMap.vue';
import RestaurantsMap from './components/RestaurantsMap.vue';
import SigmaHeader from './components/SigmaHeader.vue';
</script>

<template>
  <main>
    <SigmaHeader class="generic-component" />
    <OldStudentsMap class="generic-component" id="oldStudentsMap" />
    <RestaurantsMap class="generic-component" id="restaurantsMap" /> 
    <LeafletTutorial class="generic-component" id="contact" /> 
    LeafletTutorial
  </main>
  <footer class="generic-component">{{json.text}}</footer>
</template>

<style scoped>
</style>
