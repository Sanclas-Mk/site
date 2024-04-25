<script setup>
import Botao from "../../Botao.vue";
</script>

<template>
  <main class="bg-[#0E100F] text-center h-[500px]">
    <!-- Textos -->
    <div class="font-principal text-white pt-10 relative">
      <h1 class="text-[24px] font-semibold pb-4">Bem-vindo a MK Sanclas</h1>
      <h2 class="text-[18px] font-semibold leading-10">
        Nós executamos
        <span class="bg-[#D4FE6C] text-black px-2 py-1 rounded-full">
          a novidade</span
        >
        do
        <br />
        mundo tecnológico <br />
        E encaixar você neste mundo <br />
        <span class="bg-[#EEF2FF] text-black px-2 py-1 rounded-full"
          >é a nossa prioridade!</span
        >
      </h2>
    </div>

    <!-- Imagem -->
    <img src="" alt="" />

    <!-- Botão -->
    <Botao
      borda="border-[#FBCFE8] w-[172px] -translate-x-[105px] -translate-y-3"
      bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[0px_2px_20px_-9px_rgba(232,46,232,1)]"
      icone="fa-solid fa-arrow-down pl-2 pt-1"
      texto="O que fazemos?"
      class="py-10"
    />
  </main>
</template>

