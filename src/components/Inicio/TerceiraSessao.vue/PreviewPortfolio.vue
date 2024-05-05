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
      start: "top 80%",
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
      start: "-180px 80%",
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
    id="portfolio"
    class="bg-[#0E100F] text-white text-center px-8 py-20 font-principal md:px-20 lg:text-left relative projetos"
  >
    <!-- Texto -->
    <div class="pb-4 textsProjetos">
      <h1
        class="font-semibold text-[20px] px-2 md:text-[26px] xl:text-[30px] titleProjeto"
      >
        Na Mk Sanclas, não apenas construímos sites, <br />
        criamos experiências digitais excepcionais.
      </h1>
      <h2
        class="mt-6 font-medium md:text-[18px] lg:hidden titleProjeto text-[#B0B0B0]"
      >
        Conheça alguns dos nossos projetos:
      </h2>
      <!-- Texto -->
      <h2
        class="font-medium text-[18px] xl:text-[20px] xl:mr-[350px] pt-6 pl-2 text-white/80 max-lg:hidden text-[#B0B0B0] textProjetos"
      >
        Cada site que entregamos é uma obra-prima única, projetada para cativar
        seu público-alvo e destacar sua marca de maneira memorável.
      </h2>
    </div>

    <!-- Projetos/ Imagens -->
    <Projetos class="projetosInfo lg:pt-20" />

    <!-- Texto -->
    <h2
      class="font-medium pt-6 md:text-[18px] lg:hidden text-[#B0B0B0] textProjetos"
    >
      Cada site que entregamos é uma obra-prima única, projetada para cativar
      seu público-alvo e destacar sua marca de maneira memorável.
    </h2>
  </div>
</template>