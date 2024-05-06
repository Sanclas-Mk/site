<script setup>
import Pacote from "./Pacote.vue";
import { gsap, ScrollTrigger } from "gsap/all";
import { onMounted } from "vue";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

onMounted(() => {
  let mm = gsap.matchMedia();
  mm.add("(max-width: 1023px)", () => {
    let tlImportancia = gsap.timeline({
      scrollTrigger: {
        trigger: ".pacotes-grupo",
        start: "-120px center",
        end: "bottom center",
      },
    });
    tlImportancia.from(".pacotes-grupo .pacote1", {
      y: 100,
      opacity: 0,
      duration: 0.8,
    });

    let tlPacote2 = gsap.timeline({
      scrollTrigger: {
        trigger: ".pacote2",
        start: "-200px 80%",
        end: "bottom center",
      },
    });
    tlPacote2.from(".pacote2", {
      y: 100,
      opacity: 0,
      duration: 0.8,
    });

    let tlPacote3 = gsap.timeline({
      scrollTrigger: {
        trigger: ".pacote3  ",
        start: "-220px 80%",
        end: "bottom center",
      },
    });
    tlPacote3.from(".pacote3", {
      y: 100,
      opacity: 0,
      duration: 0.8,
    });
  });
  mm.add("(min-width: 1024px)", () => {
    gsap.from(".pacotes-grupo", {
      y: 100,
      opacity: 0,
      duration: 0.8,
      scrollTrigger: {
        trigger: ".pacotes-grupo",
        start: "-200px center",
        end: "top center",
      },
    });
  });
});

const beneficiosEssencial = [
  "Design Responsivo",
  "Otimização rápida",
  "Navegação One-page",
  "1 Página",
  "4 Seções",
  "1 Funcionalidade",
  "Aplicamos o seu conteúdo",
];

const beneficiosAvancado = [
  "Design Responsivo",
  "Otimização rápida",
  "Site dinâmico",
  "Menu/Barra de navegação",
  "5 Páginas",
  "7 Seções",
  "5 Funcionalidades",
  "Formulário de Contato",
  "Aplicamos o seu conteúdo",
];

const beneficiosPremium = [
  "Integração com banco de dados",
  "Chat de Suporte",
  "Site dinâmico",
  "Design Responsivo",
  "Otimização rápida",
  "Menu/Barra de navegação",
  "7 Páginas",
  "11 Seções",
  "7 Funcionalidades",
  "Formulário de Contato",
  "Aplicamos o seu conteúdo",
];
</script>

<template>
  <div
    class="pacotes-grupo md:px-20 lg:px-0 lg:flex lg:space-x-4 lg:mx-4 xl:justify-center"
  >
    <Pacote
      class="pacote1"
      tags="Portfólio | Página única..."
      estilo="p-6 border-[1px] border-black/50 "
      pacote="Essencial"
      valor="R$ 650,00"
      estiloDescricao="text-black/80"
      descricao="Um modo direto ao ponto. Para aqueles que buscam praticidade."
      botao="bg-[#e7c4ee] hover:bg-[#DBDFFA] text-black shadow-[0px_2px_14px_-9px_rgba(92,92,92,1)]"
      :beneficios="beneficiosEssencial"
      estiloBeneficios="text-black/80"
    />
    <Pacote
      class="pacote2"
      tags="Landing Page | Institucional..."
      estilo="p-6 bg-[#252525] text-white"
      pacote="Avançado"
      valor="R$ 1250,00"
      estiloDescricao="text-white/80"
      descricao="Um modo mais elaborado e refinado. Para aqueles que buscam algo a mais."
      botao="bg-[#e7c4ee] hover:bg-[#DBDFFA] text-black shadow-[0px_2px_14px_-9px_rgba(92,92,92,1)]"
      :beneficios="beneficiosAvancado"
      estiloBeneficios="text-white/80"
    />
    <Pacote
      class="pacote3"
      tags="Blog | E-commerce..."
      estilo="p-6 border-[1px] border-black/50"
      pacote="Premium"
      valor="R$ 3500,00"
      estiloDescricao="text-black/80"
      descricao="Um modo completo e bem otimizado. Para aqueles que buscam completude."
      botao="bg-[#e7c4ee] hover:bg-[#DBDFFA] text-black shadow-[0px_2px_14px_-9px_rgba(92,92,92,1)]"
      :beneficios="beneficiosPremium"
      estiloBeneficios="text-black/80"
    />
  </div>
</template>