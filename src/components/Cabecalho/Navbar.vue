<script setup>
import { useRoute } from "vue-router";

const route = useRoute(); // Obtenha o objeto de rota atual

// Função para verificar se a rota atual corresponde ao link
const isRouteActive = (routeName) => {
  return route.name === routeName;
};

const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<template>
  <div
    class="flex flex-col md:flex-row md:space-x-8 px-8 pt-4 leading-[50px] font-principal font-medium text-white text-[20px] md:pb-2 lg:pb-0 lg:pt-2"
  >
    <a
      class="hover:text-[#e7c4ee]"
      :class="{
        'text-[#e7c4ee]': isRouteActive('home'),
      }"
      href="/"
      >Início</a
    >
    <router-link
      class="hover:text-[#e7c4ee]"
      :class="{
        'text-[#e7c4ee]': isRouteActive('about'),
      }"
      to="/about"
      >Quem somos</router-link
    >
    <a
      class="hover:text-[#e7c4ee]"
      :class="{
        'text-[#e7c4ee]': isRouteActive('portfolio'),
      }"
      href="/#portfolio"
      >Portfólio</a
    >
    <a
      class="hover:text-[#e7c4ee]"
      :class="{
        'text-[#e7c4ee]': isRouteActive('pacotes'),
      }"
      href="/#pacotes"
      >Pacotes</a
    >
  </div>
</template>
