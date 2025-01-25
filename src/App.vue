<script setup>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import OurRecomendations from './components/OurRecomendations.vue'
import TrendingStays from './components/TrendingStays.vue'
import FAQs from './components/FAQs.vue';
import FooterLanding from './components/FooterLanding.vue';

</script>

<template>

  <Navbar></Navbar>

  <!--Content-->
  <section class="w-full h-auto">
    <Home></Home>
    <OurRecomendations></OurRecomendations>
    <TrendingStays></TrendingStays>
    <FAQs></FAQs>
  </section>
  <FooterLanding></FooterLanding>  
</template>
