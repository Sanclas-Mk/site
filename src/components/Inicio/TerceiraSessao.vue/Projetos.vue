<template>
  <div>
    <slide-container :projects="projects"></slide-container>
  </div>
</template>

<script setup>
import SlideContainer from "./SlideContainer.vue";

const projects = [
  {
    title: "Pizzaria",
    image: "./images/projetos/PizzariaDesktop.png",
    imagemobile: "./images/projetos/PizzariaMobile.png",
    alt: "",
  },
  {
    title: "Bipp",
    image: "./images/projetos/BippDesktop.png",
    imagemobile: "./images/projetos/BippMobile.png",
  },
  {
    title: "ED - Educação a Distância",
    image: "./images/projetos/EDDesktop.png",
    imagemobile: "./images/projetos/EDMobile.png",
  },
  {
    title: "Site de Roupas E-commerce",
    image: "./images/projetos/EcommerceDesktop.png",
    imagemobile: "./images/projetos/EcommerceMobile.png",
  },
];
</script>
