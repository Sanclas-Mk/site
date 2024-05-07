<script setup>
import { onMounted } from "vue";
import Card from "../../Card.vue";

onMounted(() => {
  const botao = document.querySelector(".cardImportancia");
  const gradienteOriginal = "10px 5px 5px black";
  const gradienteHover = "10px 5px 5px black";

  botao.addEventListener("mouseover", () => {
    gsap.to(botao, { boxShadow: gradienteHover, duration: 0.8 });
  });

  botao.addEventListener("mouseleave", () => {
    gsap.to(botao, { boxShadow: gradienteOriginal, duration: 0.8 });
  });
});
</script>

<template>
  <div class="md:mx-20 md:text-[19px] lg:mx-0 lg:grid lg:grid-cols-2 lg:gap-4">
    <router-link to="/about">
      <Card
        abbrIS="Saiba mais"
        estilo="rounded-[10px] py-4 px-2 mt-2 lg:mt-5 lg:px-4 lg:pt-8 bg-[#D4FE6C] hover:shadow-[0px_2px_14px_-6px_rgba(34,230,53,0.68)] cardImportancia"
        estiloTitulo="font-bold"
        titulo="Credibilidade e Profissionalismo"
        texto="Pesquisas indicam que cerca de 75% dos consumidores julgam a credibilidade de uma empresa com base no design do seu site..."
        textoEstilo="max-lg:hidden "
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </router-link>

    <router-link to="/about">
      <Card
        abbrIS="Saiba mais"
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:px-4 lg:pt-8 border border-black hover:shadow-[0px_2px_14px_-6px_rgba(92,92,92,1)] cardImportancia"
        estiloTitulo="font-bold"
        titulo="Marketing e Custos Reduzidos"
        texto="Estatísticas revelam que o marketing digital tem um ROI (retorno sobre investimento) 2.5 vezes maior do que o marketing tradicional..."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </router-link>

    <router-link to="/about">
      <Card
        abbrIS="Saiba mais"
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black hover:shadow-[0px_2px_14px_-6px_rgba(92,92,92,1)] cardImportancia"
        estiloTitulo="font-bold"
        titulo="Acesso 24 horas"
        texto="Um site permite que sua empresa esteja disponível 24 horas por dia, 7 dias por semana, para atender às necessidades mesmo..."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </router-link>

    <router-link to="/about">
      <Card
        abbrIS="Saiba mais"
        estilo="rounded-[10px] py-4 px-2 mt-5 lg:mt-0 lg:px-4 lg:pt-8 border border-black hover:shadow-[0px_2px_14px_-6px_rgba(92,92,92,1)] cardImportancia"
        estiloTitulo="font-bold"
        titulo="Destaque e Relevância"
        texto="Ter um site pode ajudar a diferenciar sua empresa da concorrência e garantir sua relevância em um mercado cada vez..."
        textoEstilo="max-lg:hidden"
        seta="fa-solid fa-arrow-right-long"
        saiba="Saiba mais"
        estiloSaiba="flex items-center lg:pb-4 lg:space-x-5"
      />
    </router-link>
  </div>
</template>