<template>
  <div
    :class="estilo"
    class="max-lg:flex items-center space-x-4 relative"
    @mouseover="onMouseOver"
    @mouseleave="onMouseLeave"
  >
    <div class="flex items-center space-x-4 font-principal">
      <i class="text-[24px] ml-1" :class="icone"></i>
      <div class="pr-4">
        <p class="lg:text-[20px]" :class="estiloTitulo">
          {{ titulo }}
        </p>
        <p v-if="texto" :class="textoEstilo" class="py-4">
          {{ texto }}
        </p>
      </div>
    </div>
    <div :class="estiloSaiba">
      <p class="font-bold max-lg:hidden">{{ saiba }}</p>
      <i :class="seta" ref="seta" class="right-4 pt-[2px] max-lg:absolute"></i>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    estilo: String,
    icone: String,
    titulo: String,
    estiloTitulo: String,
    texto: String,
    textoEstilo: String,
    seta: String,
    saiba: String,
    estiloSaiba: String,
  },
};
</script>
