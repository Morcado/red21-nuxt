<script setup>
import { defineComponent } from 'vue';

// =========================================================================
  // To use local images, you need to import them first.
  // Replace these example paths with the actual paths to your images in the 'assets' folder.
  // =========================================================================
  import mountainImage from '~/assets/planes/plan-01-2025-08.jpeg';
  import urbanImage from '~/assets/planes/plan-02-2025-08.jpeg';
  import lakeImage from '~/assets/planes/plan-03-2025-08.jpeg';
  import autumnImage from '~/assets/planes/plan-04-2025-08.jpeg';
  import buildingImage from '~/assets/planes/plan-05-2025-08.jpeg';

  // Then, use the imported variables in your data array.
  const images = [
    {
      src: mountainImage,
      alt: "A scenic view of mountains",
      title: "Mountain Vista",
      description: "Breathtaking views from the highest peak."
    },
    {
      src: urbanImage,
      alt: "A quiet city street at night",
      title: "Urban Nights",
      description: "Neon lights reflecting on a wet street."
    },
    {
      src: lakeImage,
      alt: "A boat on a calm lake",
      title: "Lake Serenity",
      description: "A perfect day for sailing on the lake."
    },
    {
      src: autumnImage,
      alt: "A forest trail in autumn",
      title: "Autumn Trail",
      description: "A peaceful walk through colorful woods."
    },
    {
      src: buildingImage,
      alt: "A modern building with glass facade",
      title: "Architectural Marvel",
      description: "Innovative design and structure."
    }
  ];
</script>

<template>
 <div class="p-4 rounded-xl shadow-lg">
    <h2 class="text-4xl text-center text-white mb-4">
      Planes
    </h2>
    
    <!--
      The main carousel container.
      - `flex`: Enables Flexbox for horizontal layout.
      - `gap-4`: Adds space between carousel items.
      - `overflow-x-scroll`: Allows the content to be scrolled horizontally.
      - `snap-x`: Enables snapping behavior for a smoother scroll experience.
      - `snap-mandatory`: Ensures the scroll position snaps to the start of each child element.
      - `scroll-smooth`: Adds a smooth scrolling animation.
    -->
    <div class="flex gap-4 overflow-x-scroll snap-x snap-mandatory scroll-smooth p-2">
      <div 
        v-for="(image, index) in images" 
        :key="index"
        class="flex-none w-80 md:w-96 rounded-xl overflow-hidden shadow-md snap-center"
      >
        <!--
          The image element.
          - `w-full`: Ensures the image takes up the full width of its container.
          - `h-64`: Sets a fixed height for consistency.
          - `object-cover`: Ensures the image covers the entire space without distortion.
          - `transform hover:scale-105 transition duration-300`: Adds a subtle hover effect.
        -->
        <img
          :src="image.src"
          :alt="image.alt"
          class="w-full h-150 object-cover transform hover:scale-105 transition duration-300"
        />
        
        
      </div>
    </div>
  </div>
</template>