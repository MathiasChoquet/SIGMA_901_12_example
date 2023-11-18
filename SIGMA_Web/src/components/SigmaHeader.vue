<script setup>
import jsonData from '@/assets/sigma_header_texts.json';
</script>

<template>
  <div>
    <div class="titre">
      <div class="logo">
        <img src="@/assets/logo_ut2j.png" alt="ut2js Logo" >
      </div>
      <div class="texte">
        <h1>{{ jsonData.title }}</h1>
      </div>
      <div class="logo">
        <img src="@/assets/logo_sigma.png" alt="SIGMA Logo" >
      </div>
    </div>
    <div class="menu">
      <a href="#oldStudentsMap">Anciens élèves</a>
      <a href="#restaurantsMap">Les restaurants</a>
      <a href="#composant3">composant3</a>
      <a href="#composant4">compt4</a>
      <a href="#composant5">composant5</a>
    </div>
  </div>
</template>

<style scoped>

.titre {
    display: flex;
    align-items: center;
    @media screen and (max-width: 1024px) {
      flex-direction: column;
    }
  }

  .logo {
    flex: 1;
  }

  .logo img {
    max-width: 90%;
    height: auto;
    @media screen and (max-width: 1024px) {
      max-width: 50%;
    }
  }

  .texte {
    flex: 2;
    max-width: 100%;
    text-transform: uppercase;
  }

  .menu {
    display: flex;
    justify-content: space-between;
    padding: 5px; /* Ajustez la valeur selon vos besoins */
    margin: auto; /* Pour centrer le menu */
    flex-direction: row;
    font-size: 1.2rem;

        /* Ajout d'une media query pour rendre le menu vertical sur des écrans plus petits */
    @media screen and (max-width: 1024px) {
      flex-direction: column;
    }
  }

  .menu a {
    color: rgb(21, 44, 106);
    flex: 1;
    border: 1px solid #ccc;
    text-align: center;
    padding: 0 10px; /* Ajustez la valeur selon vos besoins */
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
  }


</style>
