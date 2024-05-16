<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
import { gsap, ScrollTrigger } from "gsap/all";

gsap.registerPlugin(ScrollTrigger);

ScrollTrigger.defaults({
  toggleActions: "play none play reverse",
});

const botaoFazemosTotal = ref(null);
const botaoFazemos = ref(null);
const imgs = ref(null);
const textoInicio = ref(null);

const setupScrollTriggers = () => {
  gsap
    .timeline({
      scrollTrigger: {
        trigger: botaoFazemosTotal.value,
        start: "-200px center",
        end: "bottom center",
      },
    })
    .from(botaoFazemosTotal.value, {
      y: -100,
      opacity: 0,
      duration: 0.8,
    })
    .to(botaoFazemos.value, {
      y: 14,
      x: 20,
      duration: 0.5,
    });

  gsap
    .timeline({
      scrollTrigger: {
        trigger: imgs.value,
        start: "-120px center",
        end: "bottom center",
      },
    })
    .from(".imgShow", {
      x: "-100px",
      duration: 0.8,
      opacity: 0,
    });

  gsap
    .timeline({
      scrollTrigger: {
        trigger: imgs.value,
        start: "-320px center",
        end: "bottom center",
      },
    })
    .from(textoInicio.value, {
      y: "-100px",
      duration: 0.8,
      opacity: 0,
    });
};

const handleHover = (botao, gradiente) => {
  if (botao) {
    gsap.to(botao, { backgroundImage: gradiente, duration: 0.8 });
  }
};

onMounted(() => {
  document.addEventListener("visibilitychange", () => {
    if (document.visibilityState === "visible") {
      ScrollTrigger.refresh();
    }
  });

  window.addEventListener("resize", () => {
    ScrollTrigger.refresh();
  });

  setupScrollTriggers();

  const botao = botaoFazemos.value;
  const gradienteOriginal = "linear-gradient(to right, #8B9EFF, #EAEDFF)";
  const gradienteHover = "linear-gradient(to right, #8B9EFF, #8B9EFF)";

  if (botao) {
    botao.addEventListener("mouseover", () =>
      handleHover(botao, gradienteHover)
    );
    botao.addEventListener("mouseleave", () =>
      handleHover(botao, gradienteOriginal)
    );
  }
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", () => {
    ScrollTrigger.refresh();
  });

  document.removeEventListener("visibilitychange", () => {
    if (document.visibilityState === "visible") {
      ScrollTrigger.refresh();
    }
  });
});
</script>

<template>
  <main class="bg-[#0E100F] text-center">
    <div class="lg:flex lg:justify-center xl:space-x-20 lg:text-left">
      <!-- Textos -->
      <div>
        <div
          ref="textoInicio"
          class="font-principal text-white relative xl:text-left lg:w-[430px] xl:w-[700px] mx-4 md:mx-14 xl:mx-0 xl:pl-32 rounded-[4px] pt-10 xl:py-4 lg:pt-[100px] xl:pt-[120px]"
        >
          <h1
            class="text-[24px] md:text-[30px] xl:text-[40px] font-semibold pb-4 textoInicio"
          >
            Nós executamos
            <span class="text-[#B2F900] px-2 py-1 rounded-full">
              a novidade</span
            >
            <br class="xl:hidden" />
            do mundo tecnológico. <br />
            E encaixar você neste mundo <br />é a nossa
            <span class="text-[#B2F900] px-2 py-1 rounded-full"
              >prioridade!</span
            >
          </h1>
          <h2
            class="md:text-[18px] xl:text-[24px] text-[#C2C2C2] font-medium leading-8 pt-4 md:px-[150px] lg:px-0 textoInicio"
          >
            Desenvolvemos sites personalizados com o estilo do seu negócio e com
            o que há de mais atual no mundo da tecnologia.
          </h2>
        </div>
      </div>
      <!-- Imagem -->
      <div ref="imgs" class="mt-14 imgs mx-6">
        <img
          class="min-h-[200px] max-h-[280px] md:max-h-[400px] xl:max-h-[550px] w-auto max-lg:mx-auto max-lg:mb-10 imgShow"
          src="/images/projetos/expor.webp"
          alt="Dois celulares gigantes meio inclinados um em cima do outro. O celular que está em cima é um protótipo de um site de esmaltes que tem como destaque uma mulher sorrindo com as unhas pintadas olhando para o lado esquerdo. O segundo celular é um protótipo de um site e-commerce de venda de roupas."
        />
      </div>
    </div>

    <!-- Botão -->
    <div ref="botaoFazemosTotal" class="pb-20 lg:pb-20 botaoFazemosTotal">
      <div class="z-0 relative">
        <span
          class="h-12 border absolute border-[#FBCFE8] w-[200px] h-[40px] -translate-x-[102px] md:w-[240px] md:-translate-x-[122px] md:h-[45px]"
        ></span>
      </div>
      <div class="z-10 relative">
        <a href="#beneficios">
          <button
            ref="botaoFazemos"
            class="py-2 px-4 font-principal font-bold text-24 flex mx-auto bg-gradient-to-r from-[#8B9EFF] to-[#EAEDFF] text-black shadow-[1px_5px_10px_-5px_rgba(136,136,230,1)] botaoFazemos md:text-[20px]"
          >
            <p>O que oferecemos?</p>
            <abbr title="Veja os nossos serviços"
              ><i class="fa-solid fa-arrow-down pl-2 pt-1"></i
            ></abbr>
          </button>
        </a>
      </div>
    </div>
  </main>
</template>

