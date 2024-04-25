<script setup>
import Card from "../../Card.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted, ref } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: ".caixa",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlTitle.from(".texts .title", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });

  let tlCards = gsap.timeline({
    scrollTrigger: {
      trigger: ".cards",
      start: "-120px 80%",
      end: "bottom center",
    },
  });
  tlCards.from(".cards .card", {
    x: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });
});
</script>

<template>
  <div class="text-center font-principal px-8 py-20 font-semibold caixa">
    <!-- Texto -->
    <div class="texts">
      <h1 class="text-[20px] title">
        Desbloqueie o Potencial da sua Presença Online com um
        <span class="bg-[#E2A6FF] px-2 rounded-full">site</span> da Mk Sanclas!
      </h1>
      <h2 class="pt-4 font-medium title">
        A Mk Sanclas se destaca por oferecer soluções que superam opções
        genéricas prontas para uso, proporcionando uma abordagem sob medida para
        cada cliente com:
      </h2>
    </div>

    <!-- Cards com os Benefícios -->
    <div class="cards">
      <Card
        estilo="bg-[#171615] text-white py-5 px-4 mt-7 rounded-[8px] card"
        icone="fa-regular fa-paper-plane"
        texto="Sites Personalizados"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4 mt-4 rounded-[8px] card"
        icone="fa-regular fa-circle-check"
        texto="Técnicas SEO"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4 mt-4 rounded-[8px] card"
        icone="fa-regular fa-comments"
        texto="Suporte Eficiente"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4 mt-4 rounded-[8px] card"
        icone="fa-regular fa-handshake"
        texto="Serviços de Manutenção"
      />
    </div>
  </div>
</template>
