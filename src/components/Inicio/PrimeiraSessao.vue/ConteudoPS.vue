<script setup>
import Botao from "../../Botao.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlButton = gsap.timeline({
    scrollTrigger: {
      trigger: ".botaoFazemosTotal",
      start: "top center",
      end: "bottom center",
    },
  });
  tlButton
    .from(".botaoFazemosTotal", {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(".botaoFazemos", {
      y: 14,
      x: 20,
      duration: 0.5,
    });
});
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
      borda="border-[#FBCFE8] w-[172px] h-[40px] -translate-x-[105px]"
      bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[0px_2px_20px_-9px_rgba(232,46,232,1)] ml-20 botaoFazemos"
      icone="fa-solid fa-arrow-down pl-2 pt-1"
      texto="O que fazemos?"
      class="py-10 botaoFazemosTotal"
    />
  </main>
</template>

