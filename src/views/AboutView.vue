<script setup>
import Botao from "../components/Botao.vue";
import ImportanciaAbout from "../components/About/ImportanciaAbout.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted, ref } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let tlTitle = gsap.timeline({
    scrollTrigger: {
      trigger: ".somos",
      start: "top 80%",
      end: "bottom center",
    },
  });
  tlTitle.from(".textsSomos .titleSomos", {
    y: -100,
    opacity: 0,
    duration: 0.8,
    stagger: 0.2,
  });
  let tlButton = gsap.timeline({
    scrollTrigger: {
      trigger: ".somos",
      start: "-100 center",
      end: "bottom center",
    },
  });
  tlButton
    .from(".botaoContatoSomosTotal", {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(".botaoContatoSomos", {
      y: 14,
      x: 20,
      duration: 0.5,
    });

  const botao = document.querySelector(".botaoContatoSomos");
  const gradienteOriginal = "linear-gradient(to right, #FBCFE8, #8B9EFF)";
  const gradienteHover = "linear-gradient(to right, #FBCFE8, #FBCFE8)";

  botao.addEventListener("mouseover", () => {
    gsap.to(botao, { backgroundImage: gradienteHover, duration: 0.8 });
  });

  botao.addEventListener("mouseleave", () => {
    gsap.to(botao, { backgroundImage: gradienteOriginal, duration: 0.8 });
  });
});
</script>

<template>
  <div class="somos lg:pt-10">
    <div
      class="text-center lg:text-left font-principal md:px-20 xl:px-[200px] lg:flex md:space-x-10"
    >
      <div class="textsSomos xl:px-20">
        <div class="pt-10">
          <h1
            class="text-[26px] md:text-[28px] xl:text-[30px] font-bold titleSomos"
          >
            Quem somos?
          </h1>
          <h2
            class="font-semibold md:text-[18px] xl:text-[20px] pb-6 pt-4 titleSomos"
          >
            Conheça a Mk Sanclas!
          </h2>
        </div>
        <div class="px-4 lg:px-0 lg:text-justify py-4 titleSomos">
          <p>
            Bem-vindo à Mk Sanclas, uma empresa especializada no Desenvolvimento
            de Sites, que começou com um jovem casal sonhador. Nosso objetivo é
            entregar o que há de mais novo no mundo da tecnologia web para os
            nossos clientes. Mantendo a novidade, a eficiência, a beleza e
            satisfação para aqueles que decidem fechar negócio conosco!
          </p>
          <p class="pt-10 max-md:hidden lg:hidden">
            Fizemos pesquisas e observamos que muitas empresas fazem trabalhos
            comuns que não levam os seus clientes a um novo patamar. E decidimos
            entrar no mercado para mudar isso! Queremos destacar nossos clientes
            com o nosso trabalho. E por isso buscamos fazer projetos de
            qualidade.
          </p>
        </div>
        <Botao
          borda="border-black w-[230px] -translate-x-[118px] -translate-y-[1px]"
          bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 mx-auto botaoContatoSomos"
          icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
          texto="Entrar em Contato!"
          class="py-10 md:pb-0 text-[18px] text-center botaoContatoSomosTotal"
        />
      </div>
      <div>
        <img
          class="h-auto max-lg:hidden lg:w-[2000px] pt-10 md:pt-0"
          src="/images/logoMKSanclasPreta.png"
          alt="Logo Mk Sanclas"
        />
      </div>
    </div>
    <div><importancia-about id="importancia" /></div>
  </div>
</template>


