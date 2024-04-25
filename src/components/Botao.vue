<template>
  <div>
    <div class="z-0 relative">
      <span :class="borda" class="h-10 border absolute"></span>
    </div>
    <div class="z-10 relative">
      <button
        class="py-2 px-4 font-principal font-bold text-24 flex mx-auto"
        :class="bg"
      >
        <p>{{ texto }}</p>
        <i :class="icone"></i>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    texto: String,
    icone: String,
    bg: String,
    borda: String,
  },
};
</script>
