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

  const botao = document.querySelector(".botaoContato");
  const gradienteOriginal = "linear-gradient(to right, #8B9EFF, #EAEDFF)";
  const gradienteHover = "linear-gradient(to right, #8B9EFF, #8B9EFF)";

  botao.addEventListener("mouseover", () => {
    gsap.to(botao, { backgroundImage: gradienteHover, duration: 0.8 });
  });

  botao.addEventListener("mouseleave", () => {
    gsap.to(botao, { backgroundImage: gradienteOriginal, duration: 0.8 });
  });
});
</script>

<template>
  <div class="py-20 bg-gray-50 text-center font-principal">
    <div class="mx-10 lg:mx-40">
      <h1 class="font-semibold text-[20px] md:text-[26px] frase">
        Não se contente com menos. Escolha a excelência. Escolha a Mk Sanclas
        <br />
        para construir o futuro digital do seu negócio!
      </h1>
      <botao
        link="https://wa.me/message/SBOWMFDW3WJVG1"
        borda="border-black w-[216px] -translate-x-[110px] md:w-[230px] md:-translate-x-[118px]"
        bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 botaoContato"
        icone="fa-solid fa-arrow-right-long pl-2 pt-[6px]"
        texto="Entrar em contato"
        class="py-10 text-[18px] md:text-[20px] botaoContatoTotal"
      />
    </div>
  </div>
</template>