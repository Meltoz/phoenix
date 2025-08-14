<template>
<div ref="container" class="h-[600vh] w-screen bg-amber-500">
  <p class="fixed top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-4xl font-bold z-10">cc</p>
</div>
</template>
<script setup lang="ts">
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const container = ref(null);

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger);

  gsap.timeline({
    scrollTrigger: {
      trigger: container.value,
      start: 'top top', // début au haut de la page
      end: 'bottom bottom', // fin en bas de page
      scrub: true, // synchro avec le scroll
    }
  })
    // Amber → Noir a 40%
    .to(container.value, { backgroundColor: '#000000', duration: 0.02 }, 0.40)
    // Noir → Blanc a 80%
    .to(container.value, { backgroundColor: '#FEFEFE', duration: 0.02 }, 0.80);
});
</script>