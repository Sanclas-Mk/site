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
  <div class="somos">
    <div
      class="text-center font-principal px-10 lg:px-20 xl:px-40 pt-10 md:flex md:space-x-10"
    >
      <div class="textsSomos">
        <h2 class="font-medium md:text-[18px] xl:text-[20px] titleSomos">
          Conheça a Mk Sanclas
        </h2>
        <h1
          class="pb-6 pt-2 text-[20px] md:text-[26px] xl:text-[30px] font-semibold titleSomos"
        >
          Quem somos?
        </h1>
        <div class="text-center titleSomos">
          <p>
            Bem-vindo à Mk Sanclas, uma empresa especializada no Desenvolvimento
            de Sites, que começou com um jovem casal sonhador. Nosso objetivo é
            entregar o que há de mais novo no mundo da tecnologia web para os
            nossos clientes. Mantendo a novidade, a eficiência, a beleza e
            satisfação para aqueles que decidem fechar negócio conosco!
          </p>
          <p class="pt-10 max-lg:hidden">
            Fizemos pesquisas e observamos que muitas empresas fazem trabalhos
            comuns que não levam os seus clientes a um novo patamar. E decidimos
            entrar no mercado para mudar isso! Queremos destacar nossos clientes
            com o nosso trabalho. E por isso buscamos fazer projetos de
            qualidade.
          </p>
        </div>
        <Botao
          borda="border-black w-[250px] -translate-x-[140px] -translate-y-[14px]"
          bg="bg-gradient-to-r from-[#FBCFE8] to-[#8B9EFF] shadow-[0px_2px_24px_-9px_rgba(92,92,92,1)] py-3 mx-auto botaoContato"
          icone="fa-solid fa-arrow-right-long pl-4 pt-[8px] translate-y-1 -rotate-[50deg]"
          texto="Entrar em Contato!"
          class="py-10 text-[18px] botaoContatoTotal"
        />
      </div>
      <div>
        <img
          class="h-auto md:w-[2000px] md:pt-16"
          src="/images/projetos/projeto1.png"
          alt=""
        />
      </div>
    </div>
    <div id="importancia"><importancia-about /></div>
  </div>
</template>


