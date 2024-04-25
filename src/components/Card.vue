<template>
  <div :class="estilo" class="flex items-center space-x-4">
    <i class="text-[24px] ml-1" :class="icone"></i>
    <p class="font-semibold">{{ texto }}</p>
    <i :class="seta"></i>
  </div>
</template>
<script>
export default {
  props: {
    estilo: String,
    icone: String,
    texto: String,
    seta: String,
  },
};
</script>
