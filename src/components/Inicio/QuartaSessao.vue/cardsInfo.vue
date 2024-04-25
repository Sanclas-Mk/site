<script setup>
import Card from "../../Card.vue";
</script>

<template>
  <div>
    <a href="">
      <Card
        estilo="rounded-[16px] mx-4 mt-2 py-4 px-2 bg-[#D4FE6C] cardImportancia"
        texto="Credibilidade e Profissionalismo"
        seta="fa-solid fa-arrow-right"
      />
    </a>
    <a href="">
      <Card
        estilo="rounded-[16px] mx-4 py-4 px-2 mt-5 border border-black cardImportancia"
        texto="Marketing Eficiente e Custos Reduzidos"
        seta="fa-solid fa-arrow-right"
      />
    </a>
    <a href="">
      <Card
        estilo="rounded-[16px] mx-4 py-4 px-2 mt-5 border border-black cardImportancia"
        texto="Acesso 24/7"
        seta="fa-solid fa-arrow-right"
      />
    </a>
    <a href="">
      <Card
        estilo="rounded-[16px] mx-4 py-4 px-2 mt-5 border border-black cardImportancia"
        texto="Competição e Relevância"
        seta="fa-solid fa-arrow-right"
      />
    </a>
  </div>
</template>