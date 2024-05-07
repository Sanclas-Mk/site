<script setup>
import CardsAbout from "./CardsAbout.vue";
</script>

<template>
  <div class="font-principal py-20 px-8 md:px-20 xl:mx-[100px] importancia">
    <!-- Texto -->
    <div class="text-center pb-4 lg:text-left lg:mr-[300px] textsImportancia">
      <h1
        class="text-[26px] md:text-[28px] xl:text-[30px] font-semibold titleImportancia"
      >
        Por que ter um site hoje em dia?
      </h1>
      <h2
        class="font-medium py-4 md:text-[18px] xl:text-[20px] text-[#353535] titleImportancia"
      >
        Ter um site é essencial para estabelecer uma presença online sólida!
      </h2>
    </div>

    <!-- Cards com informações -->
    <cards-about class="cardsImportancia" />
  </div>
</template>