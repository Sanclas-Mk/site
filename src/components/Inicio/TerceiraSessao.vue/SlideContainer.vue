<!-- SlideContainer.vue -->
<template>
  <div class="slide-container">
    <div
      v-for="(project, index) in projects"
      :key="index"
      :class="{ active: index === currentIndex }"
      class="slide"
    >
      <slide :project="project"></slide>
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

export default {
  components: {
    Slide,
  },
  props: ["projects"],
  data() {
    return {
      currentIndex: 0,
    };
  },
  methods: {
    prevSlide() {
      if (this.currentIndex === 0) {
        this.currentIndex = this.projects.length - 1;
      } else {
        this.currentIndex--;
      }
    },
    nextSlide() {
      if (this.currentIndex === this.projects.length - 1) {
        this.currentIndex = 0;
      } else {
        this.currentIndex++;
      }
    },
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
