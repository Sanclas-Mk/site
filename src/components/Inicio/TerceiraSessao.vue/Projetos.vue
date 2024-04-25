<template>
  <div>
    <slide-container :projects="projects"></slide-container>
  </div>
</template>

<script setup>
import SlideContainer from "./SlideContainer.vue";

const projects = [
  {
    title: "Projeto 1",
    image: "/images/projetos/projeto1.png",
    imagemobile: "/images/projetos/projeto1mobile.png",
    alt: "",
  },
  {
    title: "Projeto 2",
    image: "",
    alt: "",
  },
];
</script>
