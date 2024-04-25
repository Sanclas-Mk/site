<script setup>
defineProps(["project"]);
</script>
 
<template>
  <div class="projetoCaixa">
    <h2
      class="text-[24px] font-semibold font-principal my-6 text-start border-b-2 border-[#D4FE6C] w-full"
    >
      {{ project.title }}
    </h2>
    <div class="flex justify-center">
      <img
        class="h-[200px] w-auto imgProjeto"
        :src="project.image"
        :alt="project.alt"
      />
    </div>
    <div class="flex justify-center h-14">
      <img
        class="abosolute -translate-y-40 translate-x-[110px] h-[200px] w-auto imgProjetoM"
        :src="project.imagemobile"
        :alt="project.alt"
      />
    </div>
  </div>
</template>

