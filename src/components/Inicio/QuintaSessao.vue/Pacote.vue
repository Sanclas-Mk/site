<script>
export default {
  props: {
    tags: String,
    estilo: String,
    pacote: String,
    valor: String,
    estiloDescricao: String,
    descricao: String,
    botao: String,
    beneficios: Array,
    estiloBeneficios: String,
  },
};
</script>

<template>
  <div class="m-4 lg:m-0 lg:w-[400px] xl:w-[350px]">
    <div class="flex justify-end">
      <span
        class="bg-[#202020] font-semibold text-white/90 pl-4 pr-3 py-2 rounded-tl-lg"
        >{{ tags }}</span
      >
    </div>
    <div :class="estilo" class="font-principal mb-10 rounded-md rounded-tr-[0]">
      <!-- Texto Pacote -->
      <div>
        <div class="text-[20px] font-bold">
          <h3 class="">{{ pacote }}</h3>
          <span class="text-[32px]">{{ valor }}</span>
        </div>
        <p class="py-2 font-medium" :class="estiloDescricao">{{ descricao }}</p>
      </div>
      <!-- Botão Pacote -->
      <div>
        <a href="https://wa.me/message/SBOWMFDW3WJVG1" target="_blank"
          ><button
            :class="botao"
            class="font-bold text-[20px] py-2 my-2 w-full rounded-md"
            type="button"
          >
            Começar!
          </button></a
        >
      </div>
      <!-- Benefícios do Pacote -->
      <div>
        <p class="font-semibold text-[18px] mt-4 pt-4 border-t-2">INCLUI:</p>
        <ul class="py-2 font-medium" :class="estiloBeneficios">
          <li v-for="(beneficio, index) in beneficios" :key="index">
            <i
              class="fa-solid fa-circle-check p-1 my-1 mr-2 rounded-full text-[#e7c4ee] text-[20px]"
            ></i
            >{{ beneficio }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>