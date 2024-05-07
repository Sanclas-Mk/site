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
  <div id="pacotes" class="font-principal pt-20 lg:px-0 bg-white pacotes">
    <div>
      <div
        class="text-center pb-4 lg:text-left textsPacotes px-10 lg:pr-[300px] xl:pr-[550px] xl:px-44 lg:pb-20"
      >
        <h1
          class="text-[20px] md:text-[26px] xl:text-[30px] font-semibold titlePacotes"
        >
          Maximizando sua experiência com os pacotes exclusivos da Mk Sanclas
        </h1>
        <h2 class="font-medium py-4 md:text-[18px] xl:text-[20px] titlePacotes">
          Nós temos os melhores planos para você. Uma Jornada de Benefícios e
          Eficiência!
        </h2>
      </div>
    </div>

    <pacotes-grupo />
  </div>
</template>