<script setup lang="ts">
import { ref } from 'vue';

// Reactive state to track whether the mobile menu is open or closed
const isMenuOpen = ref(false);

// Function to toggle the menu state
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const navLinks = [
  { name: "Inicio", path: "#inicio" },
  { name: "Planes", path: "#planes" },
  { name: "Normatividad", path: "#normatividad" },
  { name: "Acerca de", path: "#acerca-de" },
  { name: "Contacto", path: "#contacto" },
];

</script>

<template>
  <header class="bg-black/70 text-white shadow-lg fixed top-0 left-0 w-full z-50">
    <div class="container mx-auto flex items-center xs:justify-between md:justify-center p-4">

      <button @click="toggleMenu"
        class="md:hidden z-50 p-2 rounded-md focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
        aria-label="Toggle menu">
        <svg v-if="isMenuOpen" class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
          stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
        </svg>
        <svg v-else class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
          stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
        </svg>
      </button>
      
      <nav class="hidden md:flex space-x-6">
        <NuxtLink v-for="link in navLinks" :key="link.name" :to="link.path"
          class="hover:text-cyan-400 transition-colors duration-300">
          {{ link.name }}
        </NuxtLink>
      </nav>

      <div class="hidden md:block w-8"></div>

    </div>
  </header>

  <aside
    class="fixed md:hidden top-0 left-0 h-full w-full bg-black/60 text-white transform transition-transform duration-300 ease-in-out z-40"
    :class="isMenuOpen ? 'translate-x-0' : '-translate-x-full'">
    <nav class="flex flex-col p-4 space-y-10 mt-20">
      <NuxtLink v-for="link in navLinks" :key="link.name" :to="link.path" @click="toggleMenu"
        class="text-4xl text-center p-2 rounded-md hover:bg-gray-800/70 transition-colors duration-300">
        {{ link.name }}
      </NuxtLink>
    </nav>
  </aside>
</template>