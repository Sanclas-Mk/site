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
    y: 100,
    opacity: 0,
    duration: 0.5,
    stagger: 0.2,
  });
});
</script>

<template>
  <div class="font-principal py-20 px-8 md:px-20 bg-gray-50 importancia">
    <!-- Texto -->
    <div class="xl:mx-[100px]">
      <div class="text-center pb-4 lg:text-left lg:mr-[300px] textsImportancia">
        <h1
          class="text-[20px] md:text-[26px] xl:text-[30px] font-semibold titleImportancia"
        >
          Por que ter um site hoje em dia?
        </h1>
        <h2
          class="font-medium py-4 md:text-[18px] xl:text-[20px] text-[#353535] titleImportancia"
        >
          Ter um site é uma estratégia crucial para indivíduos e empresas por
          várias razões estatísticas e práticas:
        </h2>
      </div>
      <!-- Cards com informações -->
      <cards-info class="cardsImportancia" />
    </div>
  </div>
</template>