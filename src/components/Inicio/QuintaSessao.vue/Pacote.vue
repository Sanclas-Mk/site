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
        class="bg- font-semibold text-[#333333] pl-4 pr-3 py-2 rounded-tl-lg"
        >{{ tags }}</span
      >
    </div>
    <div
      :class="estilo"
      class="font-principal mb-10 rounded-md rounded-tr-[0] shadow-lg"
    >
      <!-- Texto Pacote -->
      <div>
        <div class="flex justify-between text-[20px] font-semibold">
          <h3>{{ pacote }}</h3>
          <span class="">{{ valor }}</span>
        </div>
        <p class="py-2 font-medium" :class="estiloDescricao">{{ descricao }}</p>
      </div>
      <!-- Botão Pacote -->
      <div>
        <a href=""
          ><button
            :class="botao"
            class="font-bold text-[20px] py-2 my-2 w-full rounded-sm"
            type="button"
          >
            Começar
          </button></a
        >
      </div>
      <!-- Benefícios do Pacote -->
      <div>
        <p class="font-semibold text-[18px]">Inclui:</p>
        <ul class="py-2 font-medium" :class="estiloBeneficios">
          <li v-for="(beneficio, index) in beneficios" :key="index">
            <i class="fa-solid fa-check px-2"></i>{{ beneficio }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>