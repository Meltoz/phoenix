<template>
  <div ref="container" class="h-[600vh] w-screen bg-amber-500">
    <p class="font-exat text-base fixed right-16 top-[30rem] z-10">© B-WEEK Entertainment</p>
    <p class="font-doctor fixed text-[17rem] right-36 bottom-48 z-30">Awakening</p>
    <p
      class="fixed -bottom-[12vh] left-1/2 transform -translate-x-1/2 font-bold whitespace-nowrap text-[17vw] z-10 font-getai"
    >
      PHOENIX
    </p>
    <img
      ref="img"
      src="/images/phoenix.png"
      class="fixed h-4/5 top-10 left-7/12 -translate-x-1/2 mix-blend-difference z-20"
    />
    <img
      src="/images/phoenix_negatif.png"
      class="fixed h-4/5 top-10 left-7/12 -translate-x-1/2 mix-blend-difference z-10"
    />
    <p class="text-xs font-exat -rotate-90 fixed z-10 top-40 -left-10">
      INITIALIZING SINGLE_01:<span class="font-bold">[AWAKENING]</span>
    </p>
    <p class="text-xs font-exat -rotate-90 fixed z-10 top-72 left-4 uppercase">
      CONTINUE sequence - <span class="font-bold">[SCROLL]</span> to proceed
    </p>

    <p ref="text" class="font-exat text-xl uppercase fixed top-40 left-52 w-2/5 z-30">
      formed by <span class="font-bold underline">ava kross</span>,
      <span class="font-bold underline">liam veyra</span>, <span class="font-bold underline"
        >noah draven</span
      >, and <span class="font-bold underline">kira solace</span> phoenix rises from neon lights
      and electric strings. Here, the past meet the pulse of tomorrow
    </p>
    <p ref="text2" class="font-exat text-xl uppercase fixed top-72 right-96 w-1/5 z-30 bg-transparent">
      blending synthawave and guitar, phoenix forges a unique sonic universe. <br/> here, the digital becomes <br /><span class="font-bold">[emotion]</span>
    </p>

    <div ref="listen" class="uppercase text-2xl space-y-5 font-exat font-medium fixed z-20 right-96 top-20">
      <h2 class=" font-bold text-5xl">[AWAKENING]<br /> — OUT now</h2>
      <div class="space-y-1">
        <p>spotify</p>
        <p>deezer</p>
        <p>youtube</p>
        <p class="font-extrabold underline">listen now</p>
      </div>

    </div>
    <div ref="external" class="bg-amber-400 left-20 fixed h-[90vh] w-full bottom-0">
      <div ref="interior" class="bg-amber-300 left-32 fixed h-[90vh] w-full -bottom-10"></div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

const container = ref(null);
const external = ref(null);
const interior = ref(null);
const text = ref(null);
const text2 = ref(null);
const img = ref(null);
const listen = ref(null);

useHead({
  title: 'Phoenix | B-Week Entertainment',
});

onMounted(() => {
  gsap.registerPlugin(ScrollTrigger);
  const tl = gsap.timeline({
    scrollTrigger: {
      trigger: container.value,
      start: 'top top',
      end: 'bottom bottom',
      scrub: true,
    },
  });

  tl.to(container.value, { backgroundColor: '#000000', color: '#FFFFFF', duration: 0.1 }, 0.3).to(
    container.value,
    { backgroundColor: '#FEFEFE', color: '#000000', duration: 0.1 },
    0.8
  );
  tl.to(external.value, { backgroundColor: '#000000', color: '#FFFFFF', duration: 0.1 }, 0.3).to(
    external.value,
    { backgroundColor: '#FAFAFA', color: '#000000', duration: 0.1 },
    0.8
  );

  tl.to(interior.value, { backgroundColor: '#000000', color: '#FFFFFF', duration: 0.1 }, 0.3).to(
    interior.value,
    { backgroundColor: '#F0F0F0', color: '#000000', duration: 0.1 },
    0.8
  );

  tl.fromTo(img.value, { opacity: 1 }, { opacity: 0, duration: 0.1 }, 0.1);

  tl.fromTo(text.value, {opacity:0 }, {opacity: 1, duration: 0.1}, 0.4)
    .to(text.value, {opacity: 0, duration: 0.1}, 0.78);

  tl.fromTo(text2.value, {opacity:0 }, {opacity: 1, duration: 0.1}, 0.4)
    .to(text2.value, {opacity: 0, duration: 0.1}, 0.78)

  tl.fromTo(listen.value, {opacity:0}, {opacity: 1, duration:0.1}, 0.8)
});
</script>