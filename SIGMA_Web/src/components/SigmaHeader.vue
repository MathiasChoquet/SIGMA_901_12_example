<script setup>
import jsonData from '@/assets/sigma_header_texts.json';
</script>

<template>
  <div class="greetings">
    <img src="@/assets/logo_sigma.png" alt="EPITA Logo" class="logo">
    <h1>{{ jsonData.title }}</h1>
    <h3>
      <a href="#oldStudentsMap">anciens élèves</a>
      <a href="#restaurantsMap">Les restaurants</a>
      <a href="#composant3">composant3</a>
      <a href="#composant4">composant4</a>
      <a href="#composant5">composant5</a>
    </h3>
  </div>
</template>

<style scoped>

.logo{
  position: relative;
  text-align: center;
  width: 100%;
}

h3 {
  font-size: 1.2rem;
}

a{
  margin-right: 10px;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

</style>
