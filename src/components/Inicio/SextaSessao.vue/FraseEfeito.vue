<script setup>
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
      trigger: ".frase",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlTitle.from(".frase", {
    y: -100,
    opacity: 0,
    duration: 0.8,
  });

  let tlButton = gsap.timeline({
    scrollTrigger: {
      trigger: ".botaoContatoTotal",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlButton
    .from(".botaoContatoTotal", {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(".botaoContato", {
      y: 14,
      x: 20,
      duration: 0.5,
    });
});
</script>

<template>
  <div class="mx-10 py-20 text-center font-principal">
    <h1 class="font-semibold text-[20px] frase">
      Não se contente com menos. Escolha a excelência. Escolha a Mk Sanclas
      <br />
      para construir o futuro digital do seu negócio.
    </h1>
    <botao
      borda="border-black w-[210px] -translate-x-[124px]"
      bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 ml-6 botaoContato"
      icone="fa-solid fa-arrow-right-long pl-2 pt-[6px]"
      texto="Entrar em contato"
      class="py-10 text-[18px] botaoContatoTotal"
    />
  </div>
</template>