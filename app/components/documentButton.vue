<script setup lang="ts">
defineProps<{
  document: string;
  name: string;
}>();


</script>

<template>

  <button class="cursor-pointer border-4 border-red-700 bg-radial from-red-800 
        from-5% to-black md:h-50 md:w-50 xs:h-30 xs:mx-auto md:mx-5 p-4 rounded-full 
        transition-all duration-200 hover:scale-110 active:scale-95 hover:bg-yellow-500">
    <div class="flex flex-col items-center">
      <img src="../assets/icons/descarga.png" alt="Down arrow" class="w-10 h-10" />
      <span class="mt-1 text-white text-sm font-semibold group-hover:text-yellow-500">
        {{ name }}
      </span>
    </div>
  </button>
</template>