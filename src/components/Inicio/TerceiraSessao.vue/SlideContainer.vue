<template>
  <div class="slide-container">
    <div
      v-for="(project, index) in projects"
      :key="index"
      :class="{ active: index === currentIndex }"
      class="slide"
    >
      <slide ref="slides" :project="project"></slide>
    </div>
    <div class="space-x-10 py-8 text-center">
      <button @click="prevSlide">
        <i
          class="fa-solid fa-chevron-left border px-3 py-2 rounded-full text-[20px] text-[#FEF2F2] hover:text-[#E2A6FF] hover:border-[#E2A6FF] xl:text-[24px]"
        ></i>
      </button>
      <button @click="nextSlide">
        <i
          class="fa-solid fa-chevron-right border px-3 py-2 rounded-full text-[20px] text-[#FEF2F2] hover:text-[#E2A6FF] hover:border-[#E2A6FF] xl:text-[24px]"
        ></i>
      </button>
    </div>
  </div>
</template>

<script>
import Slide from "./Slide.vue";
import { ref, onMounted, onBeforeUnmount } from "vue";

export default {
  components: {
    Slide,
  },
  props: ["projects"],

  setup(props) {
    const currentIndex = ref(0);
    const slides = ref([]);
    let intervalId;

    const prevSlide = () => {
      stopAutoPlay();
      currentIndex.value =
        (currentIndex.value - 1 + props.projects.length) %
        props.projects.length;

      startAutoPlay();
    };

    const nextSlide = () => {
      stopAutoPlay();
      currentIndex.value = (currentIndex.value + 1) % props.projects.length;

      startAutoPlay();
    };

    const startAutoPlay = () => {
      intervalId = setInterval(() => {
        nextSlide();
      }, 5000);
    };

    const stopAutoPlay = () => {
      clearInterval(intervalId);
    };

    onMounted(() => {
      slides.value = document.querySelectorAll(".slide");
      startAutoPlay();
    });

    onBeforeUnmount(() => {
      stopAutoPlay();
    });

    return {
      currentIndex,
      prevSlide,
      nextSlide,
    };
  },
};
</script>

<style scoped>
.slide-container {
  width: 100%;
  overflow: hidden;
}

.slide {
  display: none;
}

.slide.active {
  display: block;
}
</style>
