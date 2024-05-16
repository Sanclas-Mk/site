<script setup>
import Card from "../../Card.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { ref, onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

const caixaRef = ref(null);
const cardsRef = ref(null);

const setupAnimations = () => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: caixaRef.value,
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
      trigger: cardsRef.value,
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlCards.from(".cards .card", {
    y: 100,
    opacity: 0,
    duration: 0.5,
    stagger: 0.2,
  });
};

onMounted(() => {
  setupAnimations();
});
</script>

<template>
  <div
    id="beneficios"
    ref="caixaRef"
    class="text-center lg:text-left font-principal px-8 py-20 pt-10 md:px-20 font-semibold relative caixa xl:py-32 xl:mx-[100px]"
  >
    <!-- Texto -->
    <div class="texts lg:mr-[300px] xl:mr-[350px]">
      <h1
        class="text-[20px] md:text-[26px] xl:text-[30px] p-4 lg:px-0 border-b-2 border-[#e7c4ee] title"
      >
        Desbloqueie o Potencial da sua Presença Online com um site da Mk
        Sanclas!
      </h1>
      <h2 class="pt-4 font-medium md:text-[18px] xl:text-[20px] title">
        A Mk Sanclas se destaca por oferecer soluções que superam opções
        genéricas prontas para uso, proporcionando uma abordagem sob medida para
        cada cliente com:
      </h2>
    </div>

    <!-- Cards com os Benefícios -->
    <div
      ref="cardsRef"
      class="cards md:mx-20 lg:mx-0 pt-4 md:text-[18px] lg:grid lg:grid-cols-2 lg:gap-6 lg:mr-[120px] lg:mt-10 xl:mr-[350px] items-center"
    >
      <Card
        abbrIP="Site Personalizado"
        estilo="bg-[#171615] flex justify-center text-white py-5 px-4 mt-7 rounded-[8px] lg:mt-0 card"
        icone="fa-regular fa-paper-plane"
        titulo="Sites Personalizados"
      />
      <Card
        abbrIP="Técnicas SEO"
        estilo="border-2 border-black flex justify-center py-5 px-4 mt-4 rounded-[8px] lg:mt-0 card"
        icone="fa-regular fa-circle-check "
        titulo="Técnicas SEO"
      />
      <Card
        abbrIP="Suporte Eficiente"
        estilo="border-2 border-black flex justify-center py-5 px-4 mt-4 rounded-[8px] lg:mt-0 card"
        icone="fa-regular fa-comments"
        titulo="Suporte Eficiente"
      />
      <Card
        abbrIP="Manutenção"
        estilo="border-2 border-black flex justify-center py-5 px-4 mt-4 rounded-[8px] lg:mt-0 card"
        icone="fa-regular fa-handshake"
        titulo="Manutenção"
      />
    </div>
  </div>
</template>
