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
    image: "./images/projetos/PizzariaDesktop.webp",
    imagemobile: "./images/projetos/PizzariaMobile.webp",
    alt: "Design de um site personalizado e responsivo feito por Mk Sanclas de uma pizzaria.",
  },
  {
    title: "Bipp",
    image: "./images/projetos/BippDesktop.webp",
    imagemobile: "./images/projetos/BippMobile.webp",
    alt: "Design de site um personalizado e responsivo feito por Mk Sanclas para uma empresa chamada Bipp.",
  },
  {
    title: "ED - Educação a Distância",
    image: "./images/projetos/EDDesktop.webp",
    imagemobile: "./images/projetos/EDMobile.webp",
    alt: "Design de um site personalizado e responsivo feito por Mk Sanclas para uma instituição de educação a distância chamada ED.",
  },
  {
    title: "Site de Roupas E-commerce",
    image: "./images/projetos/EcommerceDesktop.webp",
    imagemobile: "./images/projetos/EcommerceMobile.webp",
    alt: "Design de um site personalizado e responsivo feito por Mk Sanclas para uma loja de roupas.",
  },
];
</script>
