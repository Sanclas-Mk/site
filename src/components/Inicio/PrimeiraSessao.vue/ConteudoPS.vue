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
      start: "-150px center",
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
      start: "-120px center",
      end: "bottom center",
    },
  });
  tlImg.from(".imgShow", {
    x: "-100px",
    duration: 0.8,
    opacity: 0,
  });

  let textoInicio = gsap.timeline({
    scrollTrigger: {
      trigger: ".imgs",
      start: "-120px center",
      end: "bottom center",
    },
  });
  textoInicio.from(".textoInicio", {
    y: "-100px",
    duration: 0.8,
    opacity: 0,
  });

  const botao = document.querySelector(".botaoFazemos");
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
  <main class="bg-[#0E100F] text-center lg:pt-12 xl:pt-16">
    <div
      class="xl:flex xl:justify-center xl:space-x-20 items-center xl:text-left"
    >
      <!-- Textos -->
      <div>
        <div
          class="font-principal text-white relative xl:text-left xl:w-[520px] mx-4 md:mx-14 xl:border-l-2 border-[#8888E6] xl:px-10 rounded-[4px] pt-10 xl:py-4"
        >
          <h1 class="text-[24px] md:text-[30px] font-semibold pb-4 textoInicio">
            Nós executamos
            <span class="text-[#D4FE6C] px-2 py-1 rounded-full">
              a novidade</span
            >

            <br class="xl:hidden" />
            do mundo tecnológico <br />
            E encaixar você neste mundo <br />é a nossa
            <span class="text-[#D4FE6C] px-2 py-1 rounded-full"
              >prioridade!</span
            >
          </h1>
          <h2
            class="md:text-[18px] xl:text-[20px] text-[#C2C2C2] font-medium leading-8 pt-4 md:px-[150px] lg:px-[200px] xl:px-0 textoInicio"
          >
            Fazemos sites personalizados para o seu estilo e com o que há de
            mais novo no mundo da tecnologia.
          </h2>
        </div>
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
      bg="bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[1px_5px_10px_-5px_rgba(136,136,230,1)] botaoFazemos md:text-[20px]"
      icone="fa-solid fa-arrow-down pl-2 pt-1"
      texto="O que fazemos?"
      class="pb-20 pt-10 lg:pb-20 botaoFazemosTotal"
    />
  </main>
</template>

