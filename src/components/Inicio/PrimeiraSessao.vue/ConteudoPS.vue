<script setup>
import Botao from "../../Botao.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlButton = gsap.timeline({
    scrollTrigger: {
      trigger: ".botaoFazemosTotal",
      start: "-100 center",
      end: "bottom center",
    },
  });
  tlButton
    .from(".botaoFazemosTotal", {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(".botaoFazemos", {
      y: 14,
      x: 20,
      duration: 0.5,
    });

  let tlImg = gsap.timeline({
    scrollTrigger: {
      trigger: ".imgs",
      start: "top center",
      end: "bottom center",
    },
  });
  tlImg.from(".imgShow", {
    x: "-100px",
    duration: 0.5,
    opacity: 0,
  });
});
</script>

<template>
  <main class="bg-[#0E100F] text-center">
    <div
      class="lg:flex lg:justify-center lg:space-x-10 xl:space-x-20 items-center lg:text-left xl:pt-10"
    >
      <!-- Textos -->
      <div>
        <div
          class="font-principal text-white pt-10 relative lg:text-center xl:text-left lg:w-[480px] xl:w-[520px]"
        >
          <h1 class="text-[24px] md:text-[30px] font-semibold pb-4">
            Nós executamos
            <span class="bg-[#D4FE6C] text-black px-2 py-1 rounded-full">
              a novidade</span
            >
            do
            <br class="xl:hidden" />
            mundo tecnológico <br />
            E encaixar você neste mundo <br />
            <span class="bg-[#EEF2FF] text-black px-2 py-1 rounded-full"
              >é a nossa prioridade!</span
            >
          </h1>
          <h2 class="md:text-[18px] xl:text-[20px] font-medium leading-8 pt-4">
            Fazemos sites personalizados para o seu negócio crescer ainda mais
            pela internet!
          </h2>
        </div>
        <!-- Botão -->

        <Botao
          link="#beneficios"
          borda="border-[#FBCFE8] w-[176px] h-[40px] -translate-x-[88px] md:w-[210px] md:-translate-x-[106px] md:h-[45px]"
          bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[0px_2px_20px_-9px_rgba(232,46,232,1)] botaoFazemos md:text-[20px]"
          icone="fa-solid fa-arrow-down pl-2 pt-1"
          texto="O que fazemos?"
          class="pb-0 pt-10 lg:hidden botaoFazemosTotal"
        />
      </div>
      <!-- Imagem -->
      <div class="mt-14 imgs mx-6">
        <div class="flex justify-center">
          <img
            class="min-h-[200px] max-h-[280px] xl:max-h-[300px] imgShow"
            src="/images/projetos/projeto1.png"
            alt=""
          />
        </div>
        <div class="flex justify-center h-14">
          <img
            class="abosolute -translate-y-[220px] translate-x-[110px] h-[250px] w-auto md:h-[250px] lg:h-[280px] xl:h-[300px] md:-translate-y-[230px] md:translate-x-[150px] imgShow"
            src="/images/projetos/projeto1mobile.png"
            alt=""
          />
        </div>
      </div>
    </div>

    <!-- Botão -->

    <Botao
      link="#beneficios"
      borda="border-[#FBCFE8] w-[176px] h-[40px] -translate-x-[88px] md:w-[210px] md:-translate-x-[106px] md:h-[45px] "
      bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[0px_2px_20px_-9px_rgba(232,46,232,1)] botaoFazemos md:text-[20px]"
      icone="fa-solid fa-arrow-down pl-2 pt-1"
      texto="O que fazemos?"
      class="pb-0 pt-10 lg:pb-20 botaoFazemosTotal max-lg:hidden"
    />
  </main>
</template>

