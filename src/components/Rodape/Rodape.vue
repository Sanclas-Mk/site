<script setup>
import Navbar from "../Cabecalho/Navbar.vue";
</script>


<template>
  <div class="bg-[#0E100F] font-principal">
    <div class="md:flex items-center justify-between">
      <img
        class="h-32 w-32 max-md:hidden"
        src="/images/logoMKSanclasBranca.png"
        alt=""
      />
      <Navbar class="text-[16px] leading-10 uppercase" />
    </div>
    <div class="max-lg:hidden flex items-center justify-between text-white">
      <p>
        Nós executamos a novidade do mundo tecnológico. <br />E encaixar você
        neste mundo é a nossa prioridade!
      </p>
      <div>
        <i></i>
        <i></i>
        <i></i>
      </div>
    </div>
    <div class="border-t-[1px] border-white mx-4">
      <p></p>
    </div>
  </div>
</template>