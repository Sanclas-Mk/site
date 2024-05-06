<script setup>
import { onMounted, ref } from "vue"; // Importe as funcionalidades necessárias do Vue

const currentPage = ref(""); // Referência para armazenar a página atual

// Função para definir a página atual com base no URL
const setCurrentPage = () => {
  const path = window.location.pathname; // Obtém o caminho atual da URL
  currentPage.value = path === "/" ? "home" : path.substring(1); // Define a página atual
};

onMounted(() => {
  setCurrentPage(); // Chama a função para definir a página atual quando o componente é montado
});
</script>

<template>
  <div
    class="flex flex-col md:flex-row md:space-x-8 px-8 pt-4 leading-[50px] font-principal font-medium text-white text-[20px] md:pb-2 lg:pb-0 lg:pt-2"
  >
    <a
      :class="{
        'hover:text-[#e7c4ee]': currentPage === 'home',
        'text-[#e7c4ee]': currentPage === 'home',
      }"
      href="/"
      >Início</a
    >
    <a
      :class="{
        'hover:text-[#e7c4ee]': currentPage === 'about',
        'text-[#e7c4ee]': currentPage === 'about',
      }"
      href="/about"
      >Quem somos</a
    >
    <a
      :class="{
        'hover:text-[#e7c4ee]': currentPage === 'portfolio',
        'text-[#e7c4ee]': currentPage === 'portfolio',
      }"
      href="/#portfolio"
      >Portfólio</a
    >
    <a
      :class="{
        'hover:text-[#e7c4ee]': currentPage === 'pacotes',
        'text-[#e7c4ee]': currentPage === 'pacotes',
      }"
      href="/#pacotes"
      >Pacotes</a
    >
  </div>
</template>
