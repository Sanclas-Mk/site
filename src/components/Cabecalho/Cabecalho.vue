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
    .from("#link4", { duration: 0.3, y: 50, opacity: 0 }, "-=0.2");
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

  const botao = document.querySelector(".botaoContato");
  const gradienteOriginal = "linear-gradient(to right, #e7c4ee, #e7c4ee)";
  const gradienteHover = "linear-gradient(to right, #8B9EFF, #8B9EFF)";

  botao.addEventListener("mouseover", () => {
    gsap.to(botao, { backgroundImage: gradienteHover, duration: 0.8 });
  });

  botao.addEventListener("mouseleave", () => {
    gsap.to(botao, { backgroundImage: gradienteOriginal, duration: 0.8 });
  });
});
</script>

<template>
  <div>
    <div
      class="bg-[#0E100F] py-4 px-7 md:px-12 lg:pl-14 lg:pr-20 lg:pb-4 flex max-lg:justify-between items-center"
    >
      <img
        class="h-[55px] w-auto md:h-[65px]"
        src="/logoMKBranca.ico"
        alt="Logo da Mk Sanclas, empresa de desenvolvimento de sites"
      />
      <button type="button" @click="toggleMenu">
        <i
          v-if="!isMenuOpen"
          class="fa-solid fa-bars text-white text-[40px] md:text-[50px] lg:hidden"
        ></i>
        <i v-else class="fa-solid fa-x text-white text-[30px] lg:hidden"></i>
      </button>
      <Navbar class="max-lg:hidden lg:mx-auto text-[22px]" />
      <div class="lg:pt-2 max-lg:invisible max-lg:absolute">
        <a
          href=""
          class="p-3 font-bold font-principal bg-[#e7c4ee] rounded-lg botaoContato shadow-[1px_5px_24px_-10px_rgba(136,136,230,1)] hover:text-white"
          >Entrar em contato!</a
        >
      </div>
    </div>

    <div
      ref="menu"
      class="flex flex-col px-8 md:pt-4 leading-[60px] font-principal font-medium text-white text-[24px] text-[28px] bg-[#0E100F] overflow-hidden lg:hidden touch-none h-screen"
    >
      <div id="link1" class="hover:border-b border-[#FBCFE8] pt-14">
        <a @click="closeMenu" href="/">Início</a>
      </div>
      <div id="link2" class="hover:border-b border-[#FBCFE8]">
        <a @click="closeMenu" href="/about">Quem somos</a>
      </div>
      <div id="link3" class="hover:border-b border-[#FBCFE8]">
        <a @click="closeMenu" href="/#portfolio">Portfólio</a>
      </div>
      <div id="link4" class="hover:border-b border-[#FBCFE8]">
        <a @click="closeMenu" href="/#pacotes">Pacotes</a>
      </div>
    </div>
  </div>
</template>