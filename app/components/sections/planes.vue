<script>
import { defineComponent } from 'vue';

const images = [
  {
    name: 'Plan 1',
    image: require('~/assets/planes/plan-01-2025-08.jpeg'),
  },
  {
    name: 'Plan 1',
    image: require('~/assets/planes/plan-01-2025-08.jpeg'),
  },
  {
    name: 'Plan 1',
    image: require('~/assets/planes/plan-01-2025-08.jpeg'),
  },
  {
    name: 'Plan 1',
    image: require('~/assets/planes/plan-01-2025-08.jpeg'),
  }
];

</script>

<template>
  <div>
    <h3 class="text-2xl text-white text-center">Planes</h3>
    <p class="text-white text-center">Consulta los planes disponibles</p>
    <div class="flex flex-row">
      <div v-for="value in images">
        <img :src="value.image" :alt="value.name">
      </div>
    </div>
  </div>
</template>