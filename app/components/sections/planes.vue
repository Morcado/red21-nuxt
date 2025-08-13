<script setup lang="ts">
import type { CarrouselImage } from '~/types/carrouselImage';

import fibra1 from '~/assets/planes/plan-10-2025-08-fibra.jpeg';
import fibra2 from '~/assets/planes/plan-11-2025-08-fibra.jpeg';
import fibra3 from '~/assets/planes/plan-13-2025-08-fibra.jpeg';

import microonda1 from '~/assets/planes/plan-01-2025-08.jpeg';
import microonda2 from '~/assets/planes/plan-02-2025-08.jpeg';
import microonda3 from '~/assets/planes/plan-03-2025-08.jpeg';
import microonda4 from '~/assets/planes/plan-04-2025-08.jpeg';
import microonda5 from '~/assets/planes/plan-05-2025-08.jpeg';
import microonda6 from '~/assets/planes/plan-06-2025-08.jpeg';
import microonda7 from '~/assets/planes/plan-07-2025-08.jpeg';
import microonda8 from '~/assets/planes/plan-08-2025-08.jpeg';

const fibraImages = [fibra1, fibra2, fibra3];
const planesFibra: CarrouselImage[] = fibraImages.map((img, i) => ({
  src: img,
  alt: `Plan ${[10, 11, 13][i]}`,
  title: `Plan ${[10, 11, 13][i]}`,
}));

const microondaImages = [
  microonda1, microonda2, microonda3, microonda4,
  microonda5, microonda6, microonda7, microonda8
];

const microondaNumbers = [1, 2, 3, 4, 5, 6, 7, 8];

const planesMicroondas: CarrouselImage[] = microondaImages.map((img, i) => ({
  src: img,
  alt: `Plan ${microondaNumbers[i]}`,
  title: `Plan ${microondaNumbers[i]}`,
}));

</script>

<template>
  <div id="planes" class="xs:p-1 md:p-4 rounded-xl shadow-lg">
    <h2 class="text-4xl text-center text-white mb-4">
      Planes
    </h2>
    <p class="text-white text-center mb-4">
      Consulta los planes que tenemos de fibra optica y microondas.
    </p>
    <h3 class="text-white text-center text-2xl mb-4">Planes fibra optica</h3>
    <Carrousel v-if="fibraImages" :images="planesFibra" class="mb-8"></Carrousel>
    <h3 class="text-white text-center text-2xl mb-4">Planes microondas</h3>
    <Carrousel v-if="microondaImages" :images="planesMicroondas" class="mb-8"></Carrousel>
  </div>
</template>