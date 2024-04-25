<template>
  <button type="button">
    <i
      v-if="!isMenuOpen"
      class="fa-solid fa-bars text-white text-[40px] md:hidden"
    ></i>
    <i v-else class="fa-solid fa-x text-white text-[40px] md:hidden"></i>
  </button>
</template>