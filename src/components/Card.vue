<template>
  <div :class="estilo" class="max-lg:flex items-center space-x-4 relative">
    <div class="flex items-center space-x-4">
      <i class="text-[24px] ml-1" :class="icone"></i>
      <div class="pr-4">
        <p class="font-semibold lg:text-[20px]">{{ titulo }}</p>
        <p v-if="texto" :class="textoEstilo" class="py-4 font-medium">
          {{ texto }}
        </p>
      </div>
    </div>
    <div :class="estiloSaiba">
      <p class="font-bold max-lg:hidden">{{ saiba }}</p>
      <i :class="seta" class="right-4 pt-[2px] max-lg:absolute"></i>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    estilo: String,
    icone: String,
    titulo: String,
    texto: String,
    textoEstilo: String,
    seta: String,
    saiba: String,
    estiloSaiba: String,
  },
};
</script>
