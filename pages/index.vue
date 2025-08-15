<template>
<div ref="container" class="h-[600vh] w-screen bg-amber-500">
  <p class="font-exat text-base fixed right-20 top-[25rem] z-10">© B-WEEK Entertainment</p>
  <p class="font-doctor fixed text-[17rem] left-4/8 bottom-48 z-30">Awakening</p>
  <p class="fixed -bottom-[12vh] left-1/2 transform -translate-x-1/2 font-bold whitespace-nowrap text-[17vw] z-10 font-getai">PHOENIX</p>
  <img ref="img" src="/images/phoenix.png" class="fixed h-4/5 top-10 left-7/12 -translate-x-1/2 mix-blend-difference z-10" />
  <p class="text-xs font-exat -rotate-90 fixed z-10 top-40 -left-10">INITIALIZING SINGLE_01:<span class="font-bold">[AWAKENING]</span></p>
  <p class="text-xs font-exat -rotate-90 fixed z-10 top-72 left-4 uppercase">CONTINUE sequence - <span class="font-bold">[SCROLL]</span> to proceed</p>
  <div ref="external" class="bg-amber-400 left-20  fixed h-[90vh] w-full bottom-0 ">
    <div ref="interior" class="bg-amber-300 left-32 fixed h-[90vh] w-full -bottom-10" >
    </div>
  </div>
</div>
</template>
<script setup lang="ts">
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const container = ref(null);
const external = ref(null);
const interior = ref(null);
const img = ref(null);

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

  tl.to(container.value, { backgroundColor: '#000000', color:'#FFFFFF' , duration: 0.1 }, 0.30)
    .to(container.value, { backgroundColor: '#FEFEFE', color:'#000000' , duration: 0.1 }, 0.80);

  tl.to(external.value, { backgroundColor: '#000000', color:'#FFFFFF' , duration: 0.1 }, 0.30)
    .to(external.value, { backgroundColor: '#FAFAFA', color:'#000000' , duration: 0.1 }, 0.80);

  tl.to(interior.value, { backgroundColor: '#000000', color:'#FFFFFF' , duration: 0.1 }, 0.30)
    .to(interior.value, { backgroundColor: '#F0F0F0', color:'#000000' , duration: 0.1 }, 0.80);

  tl.fromTo(img.value, {opacity: 1}, {opacity:0, duration: 0.1}, 0.1 )
});
</script>