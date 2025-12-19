<script setup>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";

import bgSection from '../assets/images/Section/bgSection.png'


// Import Hero Content Component
import HeroContent from '../components/homeComponents/heroContent.vue'
import MainContent from "../components/homeComponents/mainContent.vue"

</script>

<template>
  <div class="min-h-screen flex flex-col bg-black relative">
    <!-- HERO SECTION sebagai Background Fixed -->
    <div
      class="fixed inset-0 bg-cover bg-center z-0"
      :style="{ backgroundImage: `url(${bgSection})` }"
    >
      <!-- Gradient Overlay -->
      <div class="absolute inset-0 bg-linear-to-b from-black/70 via-black/60 to-black/80"></div>
    </div>

    <!-- Navbar Fixed di dalam Hero -->
    <div class="fixed top-0 left-0 right-0 z-50 px-4 pt-4 lg:max-w-5xl mx-auto w-full">
      <Navbar />
    </div>

    <!-- Hero Content -->
    <HeroContent />

    <!-- KONTEN UTAMA - Dimulai setelah Hero -->
    <MainContent/>

    <Footer />
  </div>
</template>

<style scoped>
.mt-screen {
  margin-top: 10vh;
}
</style>