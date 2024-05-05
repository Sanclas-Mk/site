<script setup>
import Navbar from "../Cabecalho/Navbar.vue";
import RedesSociais from "../RedesSociais.vue";
</script>


<template>
  <div class="max-md:text-center bg-[#0E100F] font-principal lg:px-20">
    <div class="px-4 md:flex items-center justify-between">
      <img
        class="h-32 w-32 max-md:mx-auto"
        src="/images/logoMKSanclasBranca.png"
        alt=""
      />
      <redes-sociais class="md:hidden text-[28px] space-x-2" />
      <Navbar
        class="text-[16px] md:text-[18px] max-md:leading-[40px] max-md:pb-4"
      />
    </div>
    <div
      class="md:flex justify-between items-center border-t-[1px] border-white/10 md:px-4 lg:px-10 mx-4 py-4 text-white mx-8"
    >
      <p class="text-white/50 text-[12px] md:text-[14px] lg:text-[16px]">
        Todos os direitos reservados © 2024 Mk Sanclas
      </p>
      <redes-sociais class="max-md:hidden" />
    </div>
  </div>
</template>