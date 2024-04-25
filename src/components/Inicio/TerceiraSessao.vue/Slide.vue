<!-- Slide.vue -->
<template>
  <div class="">
    <h2
      class="text-[24px] font-semibold font-principal my-6 text-start mx-5 border-b-2 border-[#D4FE6C]"
    >
      {{ project.title }}
    </h2>
    <div class="flex justify-center">
      <img class="h-[200px] w-auto" :src="project.image" :alt="project.alt" />
    </div>
    <div class="flex justify-center h-14">
      <img
        class="abosolute -translate-y-40 translate-x-[110px] h-[200px] w-auto"
        :src="project.imagemobile"
        :alt="project.alt"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: ["project"],
};
</script>
