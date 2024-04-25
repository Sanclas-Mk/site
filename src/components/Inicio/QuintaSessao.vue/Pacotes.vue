<script setup>
import PacotesGrupo from "./PacotesGrupo.vue";
import botao from "../../Botao.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: ".pacotes",
      start: "top center",
      end: "bottom center",
    },
  });
  tlTitle.from(".textsPacotes .titlePacotes", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });

  let tlButton = gsap.timeline({
    scrollTrigger: {
      trigger: ".botaoPersonalizadoTotal",
      start: "top center",
      end: "bottom center",
    },
  });
  tlButton
    .from(".botaoPersonalizadoTotal", {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(".botaoPersonalizado", {
      y: 14,
      x: 20,
      duration: 0.8,
    });
});
</script>


<template>
  <div class="font-principal py-20 bg-[#EEF2FF] pacotes">
    <div class="text-center pb-4 textsPacotes">
      <h1 class="text-[20px] font-semibold px-10 titlePacotes">
        Maximizando sua experiência com os pacotes exclusivos da Mk Sanclas
      </h1>
      <h2 class="font-medium py-4 titlePacotes">
        Uma Jornada de Benefícios e Eficiência
      </h2>
    </div>

    <pacotes-grupo />

    <div class="text-center">
      <botao
        borda="border-black w-[240px] -translate-x-[140px]  botaoPersonalizadoBorda"
        bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 botaoPersonalizado"
        icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
        texto="Pacote Personalizado"
        class="py-10 text-[18px] botaoPersonalizadoTotal"
      />
    </div>
  </div>
</template>