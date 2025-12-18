<script setup>
import { ref } from "vue";
import Logo from "../assets/images/fileFooter.png";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const navLinks = [
  { name: "Home", path: "/" },
  { name: "Services", path: "/services" },
  { name: "Our Cuts", path: "/gallery" },
  { name: "Contact", path: "/contact" },
];
</script>

<template>
  <nav class="shadow-xl top-0 z-50 w-full bg-transparent rounded-2xl">
    <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 ">
      <!-- MAIN ROW -->
      <div class="flex items-center h-20">
        <!-- LOGO (KIRI, DEMPET) -->
        <a href="/" class="sm:-ml-20 inline-flex items-center gap-2 w-fit shrink-0">
          <img
            :src="Logo"
            alt="Neat Hair Studio"
            class="hidden sm:block h-16 w-auto object-contain overflow-hidden sm:h-32 sm:mt-2.5"
          />
          <div class="leading-tight sm:-ml-20">
            <span class="block text-xl font-bold">
              <span class="text-blue-500">Neat Hair </span> <span class="text-white">Studio</span>
            </span>
            <span class="block text-sm font-medium text-white">
              be confident
            </span>
          </div>
        </a>

        <!-- PUSH KE KANAN -->
        <div class="ml-auto flex items-center">
          <!-- DESKTOP NAV -->
          <div class="hidden lg:flex items-center space-x-8">
            <a
              v-for="link in navLinks"
              :key="link.name"
              :href="link.path"
              class="text-white hover:text-blue-600 font-medium text-base transition-colors duration-200 relative group"
            >
              {{ link.name }}
              <span
                class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-600 transition-all duration-200 group-hover:w-full"
              ></span>
            </a>

            <a
              href="/booking"
              class="bg-blue-500 text-white px-6 py-2.5 rounded-xl hover:bg-zinc-800 transition-all duration-800 font-semibold shadow-md shadow-blue-500/50 hover:shadow-black/40 hover:scale-105"
            >
              Book Now
            </a>
          </div>

          <!-- MOBILE BUTTON -->
          <button
            @click="toggleMenu"
            class="lg:hidden text-zinc-800 focus:outline-none focus:ring-2 focus:ring-zinc-800 rounded-lg p-2 ml-2"
            aria-label="Toggle Menu"
          >
            <svg
              class="w-7 h-7"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                v-if="!isMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- MOBILE MENU -->
    <transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="transform -translate-y-2 opacity-0"
      enter-to-class="transform translate-y-0 opacity-100"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="transform translate-y-0 opacity-100"
      leave-to-class="transform -translate-y-2 opacity-0"
    >
      <div
        v-show="isMenuOpen"
        class="lg:hidden bg-white border-t border-gray-200 shadow-lg"
      >
        <div class="px-4 pt-4 pb-6 space-y-2">
          <a
            v-for="link in navLinks"
            :key="link.name"
            :href="link.path"
            @click="toggleMenu"
            class="block px-4 py-3 text-back hover:bg-blue-50 hover:text-blue-600 rounded-lg text-base font-medium"
          >
            {{ link.name }}
          </a>

          <a
            href="/booking"
            @click="toggleMenu"
            class="block mt-4 bg-blue-600 text-white text-center px-6 py-3 rounded-lg font-semibold shadow-md"
          >
            Book Now
          </a>
        </div>
      </div>
    </transition>
  </nav>
</template>

<style scoped>
/* Poppins font import */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap");

nav {
  font-family: "Poppins", sans-serif;
  font-weight: 500;
}
</style>
