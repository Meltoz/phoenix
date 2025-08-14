<template>
<div ref="container" class="h-[600vh] w-screen bg-amber-500">
  <p class="font-doctor fixed text-[17rem] left-4/8 bottom-60 z-10">Awakening</p>
  <p class="fixed -bottom-[5vh] left-1/2 transform -translate-x-1/2 font-bold whitespace-nowrap text-[17vw] font-getai">PHOENIX</p>
  <img src="/images/phoenix.png" class="fixed h-4/5 left-7/12 -translate-x-1/2 mix-blend-difference" />
</div>
</template>
<script setup lang="ts">
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const container = ref(null);

useHead({
  title: 'Phoenix | B-Week Entertainment'
})

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger);
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: container.value,
      start: 'top top',
      end: 'bottom bottom',
      scrub: true
    }
  });

  tl.to(container.value, { backgroundColor: '#000000', color:'#FFFFFF' , duration: 0.5 }, 0.40)
    .to(container.value, { backgroundColor: '#FEFEFE', color:'#000000' , duration: 0.5 }, 0.80);

});
</script>