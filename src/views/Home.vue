<script setup>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";
</script>

<template>
  <div class="min-h-screen flex flex-col bg-black">
    <!-- WRAPPER FLOATING NAVBAR -->
    <div class="fixed top-0 left-0 right-0 z-50 px-4 pt-4">
      <div
        class="mx-auto max-w-5xl bg-white/80 backdrop-blur-md rounded-2xl shadow-md border border-white/30"
      >
        <Navbar />
      </div>
    </div>

    <!-- KONTEN UTAMA -->
    <main class="grow pt-28"> <!-- pt-28 memberi ruang agar hero tidak tertutup navbar -->
      <!-- HERO SECTION -->
      <section
        class="bg-cover bg-center h-100 sm:h-125 md:h-150 lg:h-175 flex items-center justify-center"
        style="background-image: url('../assets/images/hero-bg.jpg')"
      >
        <div class="bg-black/50 px-6 py-10 rounded-xl text-center">
          <h1 class="text-white text-4xl sm:text-5xl md:text-6xl font-bold mb-4">
            Welcome to Neat Hair Studio
          </h1>
          <p class="text-white text-lg sm:text-xl md:text-2xl">
            Your Style, Our Passion
          </p>
        </div>
      </section>

      <!-- TAMBAHKAN SECTION LAINNYA DI SINI -->
    </main>

    <Footer />
  </div>
</template>