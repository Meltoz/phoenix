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
  gsap.fromTo(container.value, 
    {
      backgroundColor: '#f59e0b'
    },
    {
      backgroundColor: '#000000',
      duration: 1,
      ease: 'none',
      scrollTrigger: {
        trigger: 'body',
        start: '40% top',
        end: '42% top',
        scrub: 1
      }
    }
  );
  gsap.fromTo(container.value,
    {
      backgroundColor: '#000000'
    },
    {
      backgroundColor: '#FEFEFE',
      duration: 1,
      ease: 'none',
      scrollTrigger: {
        trigger: 'body',
        start: '80% top',
        end: '82% top',
        scrub: 1
      }
    }
  );
});
</script>