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
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlTitle.from(".textsPacotes .titlePacotes", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });

  gsap.from(".pacotePersonalizadoBotao", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    scrollTrigger: {
      trigger: ".pacotePersonalizadoBotao",
      start: "top 80%",
      end: "top center",
    },
  });
});
</script>


<template>
  <div id="pacotes" class="font-principal py-20 lg:px-0 bg-[#EEF2FF] pacotes">
    <div class="flex xl:justify-center xl:space-x-[110px]">
      <div
        class="text-center pb-4 lg:text-left textsPacotes px-10 lg:px-14 lg:pb-20 lg:w-[730px]"
      >
        <h1
          class="text-[20px] md:text-[26px] xl:text-[30px] font-semibold titlePacotes"
        >
          Maximizando sua experiência com os pacotes exclusivos da Mk Sanclas
        </h1>
        <h2 class="font-medium py-4 md:text-[18px] xl:text-[20px] titlePacotes">
          Uma Jornada de Benefícios e Eficiência!
        </h2>
      </div>
      <div class="text-center max-lg:hidden pacotePersonalizadoBotao">
        <botao
          borda="border-black w-[250px] -translate-x-[140px] -translate-y-[14px]"
          bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 mx-auto "
          icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
          texto="Pacote Personalizado"
          class="py-10 text-[18px] xl:mr-[100px]"
        />
      </div>
    </div>

    <pacotes-grupo />

    <div class="text-center lg:hidden">
      <botao
        borda="border-black w-[250px] -translate-x-[140px] -translate-y-[14px]"
        bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 mx-auto"
        icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
        texto="Pacote Personalizado"
        class="py-10 text-[18px]"
      />
    </div>
  </div>
</template>