<script>
import Projetos from "../TerceiraSessao.vue/Projetos.vue";

export default {
  components: {
    Projetos,
  },
};
</script>

<template>
  <div class="bg-[#0E100F] text-white text-center px-4 py-10 font-principal">
    <!-- Texto -->
    <h1 class="font-semibold text-[20px] px-10">
      Na Mk Sanclas, não apenas construímos sites,
      <div class="my-2">
        <span class="bg-[#EEF2FF] text-black rounded-full px-2 py-1"
          >criamos experiências</span
        >
      </div>
      digitais excepcionais.
    </h1>

    <!-- Projetos/ Imagens -->
    <Projetos />

    <!-- Texto -->
    <h2 class="font-medium px-10 pt-6">
      Cada site que entregamos é uma obra-prima única, projetada para cativar
      seu público-alvo e destacar sua marca de maneira memorável.
    </h2>
  </div>
</template>