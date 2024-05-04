<script setup>
import Card from "../../Card.vue";
</script>

<template>
  <div class="lg:grid lg:grid-cols-2 lg:gap-4">
    <a href="about#importancia">
      <Card
        estilo="rounded-[10px] py-4 px-2 mt-2 lg:mt-5 lg:px-4 lg:pt-8 bg-[#D4FE6C] cardImportancia"
        titulo="Credibilidade e Profissionalismo"
        texto="Pesquisas indicam que cerca de 75% dos consumidores julgam a credibilidade de uma empresa com base no design do seu site."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </a>

    <a href="about#importancia">
      <Card
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:px-4 lg:pt-8 border border-black cardImportancia"
        titulo="Marketing e Custos Reduzidos"
        texto="Estatísticas revelam que o marketing digital tem um ROI (retorno sobre investimento) 2.5 vezes maior do que o marketing tradicional."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </a>

    <a href="about#importancia">
      <Card
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black cardImportancia"
        titulo="Acesso 24/7"
        texto="Um site permite que sua empresa esteja disponível 24 horas por dia, 7 dias por semana, para atender às necessidades mesmo fora do horário comercial."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </a>

    <a href="about#importancia">
      <Card
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black cardImportancia "
        titulo="Competição e Relevância"
        texto="Ter um site pode ajudar a diferenciar sua empresa da concorrência e garantir sua relevância em um mercado cada vez mais digitalizado."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </a>
  </div>
</template>