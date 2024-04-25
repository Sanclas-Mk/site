<script setup>
import cardsInfo from "./cardsInfo.vue";

import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted, ref } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: ".importancia",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlTitle.from(".textsImportancia .titleImportancia", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });

  let tlImportancia = gsap.timeline({
    scrollTrigger: {
      trigger: ".cardsImportancia",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlImportancia.from(".cardsImportancia .cardImportancia", {
    x: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });
});
</script>

<template>
  <div class="font-principal py-20 importancia">
    <!-- Texto -->
    <div class="text-center pb-4 textsImportancia mx-6">
      <h1 class="text-[20px] font-semibold titleImportancia">
        Por que ter um site hoje em dia?
      </h1>
      <h2 class="font-medium py-4 titleImportancia">
        Criar sites é uma estratégia crucial para indivíduos e empresas por
        várias razões estatísticas e práticas:
      </h2>
    </div>

    <!-- Cards com informações -->
    <cards-info class="cardsImportancia" />
  </div>
</template>