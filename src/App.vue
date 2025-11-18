<template>
  <div>
    <Hero />

    <Future />

    <Causes />

    <Solution />

    <Action />

    <success />

    <SDGS />

    <Footer />
  </div>
</template>

<script setup>
import gsap from 'gsap';
import { SplitText, ScrollTrigger } from 'gsap/all';
gsap.registerPlugin(ScrollTrigger, SplitText)

import Hero from './components/hero.vue';
import Future from './components/future.vue';
import Causes from './components/causes.vue';
import Solution from './components/solution.vue'
import Action from './components/action.vue';
import Success from './components/success.vue';
import SDGS from './components/sdgs.vue';
import Footer from './components/footer.vue';
</script>