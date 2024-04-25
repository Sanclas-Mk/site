<script setup>
import Projetos from "../TerceiraSessao.vue/Projetos.vue";

import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted, ref } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: ".projetos",
      start: "top center",
      end: "bottom center",
    },
  });
  tlTitle.from(".textsProjetos .titleProjeto", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });

  let tlProjetos = gsap.timeline({
    scrollTrigger: {
      trigger: ".projetosInfo",
      start: "-110px center",
      end: "bottom center",
    },
  });
  tlProjetos.from(".projetosInfo", {
    x: -100,
    opacity: 0,
    duration: 0.8,
  });

  let tlText = gsap.timeline({
    scrollTrigger: {
      trigger: ".textProjetos",
      start: "-180px center",
      end: "bottom center",
    },
  });
  tlText.from(".textProjetos", {
    y: 100,
    opacity: 0,
    duration: 0.8,
  });
});
</script>

<template>
  <div
    class="bg-[#0E100F] text-white text-center px-8 py-20 font-principal projetos"
  >
    <!-- Texto -->
    <div class="pb-4 textsProjetos">
      <h1 class="font-semibold text-[20px] px-2 titleProjeto">
        Na Mk Sanclas, não apenas construímos sites, <br />
        <div class="mt-2">
          <span class="bg-[#EEF2FF] text-black rounded-full px-2 py-1"
            >criamos experiências</span
          >
          digitais excepcionais.
        </div>
      </h1>
      <h2 class="mt-6 font-medium titleProjeto">
        Conheça alguns dos nossos projetos:
      </h2>
    </div>

    <!-- Projetos/ Imagens -->
    <Projetos class="projetosInfo" />

    <!-- Texto -->
    <h2 class="font-medium pt-6 textProjetos">
      Cada site que entregamos é uma obra-prima única, projetada para cativar
      seu público-alvo e destacar sua marca de maneira memorável.
    </h2>
  </div>
</template>