<script setup>
import Pacote from "./Pacote.vue";

const pacotes = [
  {
    tags: "Portfólio | Página única...",
    estilo: "p-6 bg-white ",
    pacote: "Essencial",
    valor: "R$ 650,00",
    estiloDescricao: "text-black/80",
    descricao: "Um modo direto ao ponto. Para aqueles que buscam o rápido.",
    botao:
      "bg-[#FBCFE8] text-black shadow-[0px_2px_14px_-9px_rgba(92,92,92,1)]",
    beneficios: [
      "Design Responsivo",
      "Otimização rápida",
      "Navegação One-page",
      "1 Página",
      "4 Seções",
      "1 Funcionalidade",
      "Aplicamos o seu conteúdo",
    ],
    estiloBeneficios: "text-black/80",
  },
  {
    tags: "Landing Page | Institucional...",
    estilo: "p-6 bg-[#202020] text-white",
    pacote: "Avançado",
    valor: "R$ 1250,00",
    estiloDescricao: "text-white/80",
    descricao:
      "Um modo mais elaborado e refinado. Para aqueles que buscam algo a mais.",
    botao:
      "bg-[#FBCFE8] text-black shadow-[0px_2px_18px_-9px_rgba(232,46,232,1)]",
    beneficios: [
      "Design Responsivo",
      "Otimização rápida",
      "Site dinâmico",
      "Menu/Barra de navegação",
      "5 Páginas",
      "7 Seções",
      "5 Funcionalidades",
      "Formulário de Contato",
      "Aplicamos o seu conteúdo",
    ],
    estiloBeneficios: "text-white/80",
  },
  {
    tags: "Blog | E-commerce...",
    estilo: "p-6 bg-white",
    pacote: "Premium",
    valor: "R$ 3500,00",
    estiloDescricao: "text-black/80",
    descricao:
      "Um modo completo e bem otimizado. Para aqueles que buscam completude.",
    botao:
      "bg-[#FBCFE8] text-black shadow-[0px_2px_14px_-9px_rgba(92,92,92,1)]",
    beneficios: [
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
    ],
    estiloBeneficios: "text-black/80",
  },
];
</script>

<template>
  <Pacote
    class="m-4 mb-10 rounded-md shadow-lg"
    v-for="(pac, index) in pacotes"
    :key="index"
    :tags="pac.tags"
    :estilo="pac.estilo"
    :pacote="pac.pacote"
    :valor="pac.valor"
    :estiloDescricao="pac.estiloDescricao"
    :descricao="pac.descricao"
    :botao="pac.botao"
    :beneficios="pac.beneficios"
    :estiloBeneficios="pac.estiloBeneficios"
  />
</template>