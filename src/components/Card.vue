<template>
  <div
    :class="estilo"
    class="max-lg:flex items-center space-x-4 relative"
    @mouseover="onMouseOver"
    @mouseleave="onMouseLeave"
  >
    <div class="flex items-center space-x-4 font-principal">
      <abbr :title="abbrIP"
        ><i class="text-[24px] ml-1" :class="icone"></i
      ></abbr>
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
      <abbr :title="abbrIS"
        ><i :class="seta" ref="seta" class="right-4 top-[28px] max-lg:absolute">
        </i
      ></abbr>
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
    abbrIP: String,
    abbrIS: String,
  },
};
</script>
