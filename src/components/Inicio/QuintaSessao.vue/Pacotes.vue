<script setup>
import PacotesGrupo from "./PacotesGrupo.vue";
import botao from "../../Botao.vue";
</script>


<template>
  <div class="font-principal py-10 bg-[#EEF2FF]">
    <div class="text-center">
      <h1 class="text-[20px] font-semibold px-10">
        Maximizando sua experiência com os pacotes exclusivos da Mk Sanclas
      </h1>
      <h2 class="font-medium py-4">Uma Jornada de Benefícios e Eficiência</h2>
    </div>
    <pacotes-grupo />
    <div class="text-center">
      <botao
        borda="border-black w-[240px] -translate-x-[140px] -translate-y-3"
        bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3"
        icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
        texto="Pacote Personalizado"
        class="py-10 text-[18px]"
      />
    </div>
  </div>
</template>