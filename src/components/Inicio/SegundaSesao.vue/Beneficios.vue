<script setup>
import Card from "../../Card.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted, ref } from "vue";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  gsap.from(".title", {
    scrollTrigger: {
      trigger: ".title",
      start: "-110px 90%",
      end: "-110px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
  gsap.from(".subtitle", {
    scrollTrigger: {
      trigger: ".subtitle",
      start: "-120px 90%",
      end: "-120px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
  gsap.from(".card1", {
    scrollTrigger: {
      trigger: ".card1",
      start: "-50px 90%",
      end: "-50px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
  gsap.from(".card2", {
    scrollTrigger: {
      trigger: ".card2",
      start: "-130px 90%",
      end: "-130px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
  gsap.from(".card3", {
    scrollTrigger: {
      trigger: ".card3",
      start: "-150px 90%",
      end: "-150px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
  gsap.from(".card4", {
    scrollTrigger: {
      trigger: ".card4",
      start: "-200px 90%",
      end: "-200px 60%",

      toggleActions: "restart none reverse none",
    },
    opacity: 0,
    y: 100,
    duration: 1,
  });
});
</script>

<template>
  <div class="bg-[#FEF2F2] text-center font-principal px-8 py-10 font-semibold">
    <!-- Texto -->
    <div>
      <h1 class="text-[20px] title">
        Desbloqueie o Potencial da sua Presença Online com um
        <span class="bg-[#E2A6FF] px-2 rounded-full">site</span> da Mk Sanclas!
      </h1>
      <h2 class="pt-4 font-medium subtitle">
        A Mk Sanclas se destaca por oferecer soluções de sites personalizados
        que superam opções genéricas prontas para uso, proporcionando uma
        abordagem sob medida para cada cliente.
      </h2>
    </div>

    <!-- Cards com os Benefícios -->
    <div>
      <Card
        estilo="bg-[#171615] text-white py-5 px-4  mt-7 card1"
        icone="fa-regular fa-paper-plane"
        texto="Sites Personalizados"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4  mt-7 card2"
        icone="fa-regular fa-circle-check"
        texto="Técnicas SEO"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4  mt-7 card3"
        icone="fa-regular fa-comments"
        texto="Suporte Eficiente"
      />
      <Card
        estilo="bg-[#FEE0F1] py-5 px-4  mt-7 card4"
        icone="fa-regular fa-handshake"
        texto="Serviços de Manutenção"
      />
    </div>
  </div>
</template>
