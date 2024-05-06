<script setup>
defineProps(["project"]);
</script>
 
<template>
  <div class="pb-10 relative">
    <div
      class="border-b-2 border-[#D4FE6C] max-lg:mb-10 w-full lg:-translate-x-[250px] transform lg:-rotate-90 lg:absolute lg:w-[600px] lg:my-14"
    >
      <h2
        class="text-[24px] font-semibold font-principal my-6 text-start titleProjetos"
      >
        {{ project.title }}
      </h2>
    </div>
    <div>
      <div class="flex justify-center">
        <img
          class="min-h-[200px] max-h-[400px] w-auto xl:mr-[200px] imgProjeto"
          :src="project.image"
          :alt="project.alt"
        />
      </div>
      <div class="flex justify-center">
        <img
          class="absolute h-[230px] -translate-y-[200px] translate-x-[100px] w-auto md:h-[330px] md:-translate-y-[360px] md:translate-x-[220px] xl:translate-x-[300px] imgProjetoM"
          :src="project.imagemobile"
          :alt="project.alt"
        />
      </div>
    </div>
  </div>
</template>

