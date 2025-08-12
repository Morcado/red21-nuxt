<script setup lang="ts">
import type { CarrouselImage } from '~/types/carrouselImage';

defineProps({
  images: {
    type: Array<CarrouselImage>,
    required: true
  }
});

const carouselRef = ref<HTMLElement | null>(null);

const scrollLeft = () => {
  if (carouselRef.value) {
    const item = carouselRef.value.querySelector('.flex-none') as HTMLElement | null;
    if (item) {
      const scrollAmount = item.offsetWidth + 16; // 16px for the gap
      carouselRef.value.scrollBy({ left: -scrollAmount, behavior: 'smooth' });
    }
  }
};

// Function to scroll the carousel to the right.
const scrollRight = () => {
  if (carouselRef.value) {
    const item = carouselRef.value.querySelector('.flex-none') as HTMLElement | null;
    if (item) {
      const scrollAmount = item.offsetWidth + 16; // 16px for the gap
      carouselRef.value.scrollBy({ left: scrollAmount, behavior: 'smooth' });
    }
  }
};


</script>
<template>
  <!-- Below title of container -->
  <!--
      - `overflow-x-scroll`: Allows the content to be scrolled horizontally.
      - `snap-x`: Enables snapping behavior for a smoother scroll experience.
      - `snap-mandatory`: Ensures the scroll position snaps to the start of each child element.
    -->
  <div v-bind="$attrs" ref="carouselRef"
    class="flex gap-4 overflow-x-scroll snap-x snap-mandatory scroll-smooth md:p-2">
    <div v-for="(image, index) in images" :key="index"
      class="flex-none w-80 md:w-96 rounded-xl overflow-hidden shadow-md snap-center">
      <img :src="image.src" :alt="image.alt"
        class="w-full h-160 object-cover transform hover:scale-105 transition duration-300" />
    </div>
  </div>
  <div class="flex justify-between mt-4">

    <button @click="scrollLeft"
      class=" bg-white/80 hover:bg-white/80 transition-opacity duration-300 p-2 rounded-full shadow-lg z-10">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-800" fill="none" viewBox="0 0 24 24"
        stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M15 19l-7-7 7-7" />
      </svg>
    </button>
    <button @click="scrollRight"
      class=" bg-white/80 hover:bg-white/80 transition-opacity duration-300 p-2 rounded-full shadow-lg z-10">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-800" fill="none" viewBox="0 0 24 24"
        stroke="currentColor" stroke-width="2">
        <path stroke-linecap="round" stroke-linejoin="round" d="M9 5l7 7-7 7" />
      </svg>
    </button>
  </div>
</template>

<style scoped>
.overflow-x-scroll::-webkit-scrollbar {
  height: 8px;
}

.overflow-x-scroll::-webkit-scrollbar-track {
  background: #e5e7eb;
  border-radius: 10px;
}

.overflow-x-scroll::-webkit-scrollbar-thumb {
  background: #6b7280;
  border-radius: 10px;
}

.overflow-x-scroll {
  scrollbar-width: thin;
  scrollbar-color: #6b7280 #e5e7eb;
}
</style>