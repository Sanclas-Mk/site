<script setup>
import Card from "../Card.vue";
</script>

<template>
  <div class="md:flex flex-wrap justify-center gap-2 lg:flex lg:gap-4">
    <div class="md:grid grid-cols-2 gap-4">
      <Card
        estilo=" rounded-[10px] py-4 mt-5 lg:mt-5 lg:px-4 lg:pt-8 bg-[#D4FE6C] cardImportancia max-lg:text-center"
        estiloTitulo="font-bold text-[20px] py-2"
        titulo="Credibilidade e Profissionalismo"
        texto="Pesquisas indicam que cerca de 75% dos consumidores julgam a credibilidade de uma empresa com base no design do seu site. Ter um site profissional e bem projetado pode melhorar significativamente a percepção do público sobre sua marca e seus produtos ou serviços."
      />
      <Card
        estilo="rounded-[10px] py-4 mt-5 lg:px-4 lg:pt-8 border border-black max-lg:text-center cardImportancia"
        estiloTitulo="font-bold text-[20px] py-2"
        titulo="Marketing e Custos Reduzidos"
        texto="Estatísticas revelam que o marketing digital tem um ROI (retorno sobre investimento) 2.5 vezes maior do que o marketing tradicional.Um site oferece uma plataforma eficaz para promover seus produtos ou serviços a um custo relativamente baixo em comparação com métodos de marketing convencionais."
      />
    </div>

    <Card
      estilo="rounded-[10px] py-4 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black max-lg:text-center cardImportancia"
      estiloTitulo="font-bold text-[20px] py-2"
      titulo="Acesso 24 horas por dia"
      texto="Estudos mostram que cerca de 30% dos consumidores preferem pesquisar produtos e serviços online antes de fazer uma compra. Um site permite que sua empresa esteja disponível 24 horas por dia, 7 dias por semana, para atender às necessidades mesmo fora do horário comercial."
    />

    <Card
      estilo="rounded-[10px] py-4 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black max-lg:text-center cardImportancia"
      estiloTitulo="font-bold text-[20px] py-2"
      titulo="Destaque e Relevância"
      texto="Pesquisas demonstram que mais de 60% das pequenas empresas ainda não possuem um site. Ter um site pode ajudar a diferenciar sua empresa da concorrência e garantir sua relevância em um mercado cada vez mais digitalizado."
    />
  </div>
</template>