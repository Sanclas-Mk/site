<template>
  <div>
    <div class="z-0 relative">
      <span :class="borda" class="h-12 border absolute"></span>
    </div>
    <div class="z-10 relative">
      <a :href="link" target="_blank">
        <button
          class="py-2 px-4 font-principal font-bold text-24 flex mx-auto"
          :class="bg"
        >
          <p>{{ texto }}</p>
          <abbr :title="abbr"><i :class="icone"></i></abbr>
        </button>
      </a>
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
    link: String,
    abbr: String,
  },
};
</script>
