<script setup>
import Navbar from "./Navbar.vue";
import { ref, watchEffect, onMounted } from "vue";
import { gsap, Power4 } from "gsap";

const isMenuOpen = ref(false);
const menu = ref(null);
const links = ref(null);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
  isMenuOpen.value = false;
};

let menuTimeline;

const createMenuTimeline = () => {
  menuTimeline = gsap.timeline({ paused: true });
  menuTimeline
    .from(menu.value, { duration: 0.5, height: 0 })
    .from("#link1", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2")
    .from("#link2", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2")
    .from("#link3", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2")
    .from("#link4", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2")
    .from("#link5", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2");
};

watchEffect(() => {
  if (isMenuOpen.value && menuTimeline) {
    menuTimeline.play();
  } else if (!isMenuOpen.value && menuTimeline) {
    menuTimeline.reverse();
  }
});

onMounted(() => {
  createMenuTimeline();
});
</script>

<template>
  <div>
    <div
      class="bg-[#0E100F] pt-4 px-7 lg:pl-14 lg:pr-20 flex max-lg:justify-between items-center"
    >
      <img
        class="h-[55px]"
        src="/logoMKBranca.ico"
        alt="Logo da Mk Sanclas, empresa de desenvolvimento de sites"
      />
      <button type="button" @click="toggleMenu">
        <i
          v-if="!isMenuOpen"
          class="fa-solid fa-bars text-white text-[40px] md:hidden"
        ></i>
        <i v-else class="fa-solid fa-x text-white text-[30px] md:hidden"></i>
      </button>
      <Navbar class="max-md:hidden lg:mx-auto" />
    </div>

    <div
      ref="menu"
      class="flex flex-col px-8 pt-4 leading-[60px] font-principal font-medium text-white text-[24px] bg-[#0E100F] overflow-hidden md:hidden touch-none"
    >
      <div id="link1" class="hover:border-b border-[#FBCFE8] pt-14">
        <router-link @click="closeMenu" to="/">Início</router-link>
      </div>
      <div id="link2" class="hover:border-b border-[#FBCFE8]">
        <router-link @click="closeMenu" to="/about">Quem somos</router-link>
      </div>
      <div id="link3" class="hover:border-b border-[#FBCFE8]">
        <router-link @click="closeMenu" to="/">Portfólio</router-link>
      </div>
      <div id="link4" class="hover:border-b border-[#FBCFE8]">
        <router-link @click="closeMenu" to="/">Pacotes</router-link>
      </div>
      <div id="link5" class="hover:border-b border-[#FBCFE8]">
        <router-link @click="closeMenu" to="/">Contato</router-link>
      </div>
    </div>
  </div>
</template>