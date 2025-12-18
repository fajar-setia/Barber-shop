<script setup>
import Logo from "../assets/images/fileFooter.png";
import {
  Facebook,
  Instagram,
  Phone,
  Mail,
  MapPin,
  Clock,
} from "lucide-vue-next";
</script>

<template>
  <footer class="bg-linear-to-br from-blue-950 via-blue-900 to-blue-950 text-white">
    <!-- Main Content -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-10 sm:py-12 lg:py-16">
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12">
        
        <!-- Brand Section -->
        <div class="flex flex-col space-y-4 sm:col-span-2 lg:col-span-1">
          <img
            :src="Logo"
            alt="Neat Hair Studio"
            class="hidden sm:block h-16 sm:h-56 w-auto object-contain lg:-ml-8 lg:-mt-24 lg:-mb-16"
          />
          <p class="text-blue-200 text-sm leading-relaxed">
            Modern barbershop with classic precision. Look sharp, feel confident with our expert stylists.
          </p>
          
          <!-- Social Media - Desktop & Tablet -->
          <div class="hidden sm:flex gap-3 pt-2">
            <a
              href="https://facebook.com"
              target="_blank"
              rel="noopener"
              class="bg-blue-800/50 p-3 rounded-xl hover:bg-white hover:text-blue-900 transition-all duration-300 transform hover:scale-110 hover:shadow-lg"
              aria-label="Facebook"
            >
              <Facebook class="w-5 h-5" />
            </a>
            <a
              href="https://instagram.com"
              target="_blank"
              rel="noopener"
              class="bg-blue-800/50 p-3 rounded-xl hover:bg-white hover:text-blue-900 transition-all duration-300 transform hover:scale-110 hover:shadow-lg"
              aria-label="Instagram"
            >
              <Instagram class="w-5 h-5" />
            </a>
          </div>
        </div>

        <!-- Quick Links -->
        <nav class="flex flex-col">
          <h3 class="text-base sm:text-lg font-semibold mb-4 text-white flex items-center gap-2">
            <span class="w-1 h-6 bg-blue-400 rounded-full"></span>
            Quick Links
          </h3>
          <ul class="space-y-3">
            <li>
              <a href="/" class="text-blue-200 hover:text-white hover:pl-2 transition-all duration-200 text-sm inline-flex items-center group">
                <span class="w-0 h-0.5 bg-blue-400 mr-0 group-hover:w-4 group-hover:mr-2 transition-all duration-200"></span>
                Home
              </a>
            </li>
            <li>
              <a href="/services" class="text-blue-200 hover:text-white hover:pl-2 transition-all duration-200 text-sm inline-flex items-center group">
                <span class="w-0 h-0.5 bg-blue-400 mr-0 group-hover:w-4 group-hover:mr-2 transition-all duration-200"></span>
                Services
              </a>
            </li>
            <li>
              <a href="/gallery" class="text-blue-200 hover:text-white hover:pl-2 transition-all duration-200 text-sm inline-flex items-center group">
                <span class="w-0 h-0.5 bg-blue-400 mr-0 group-hover:w-4 group-hover:mr-2 transition-all duration-200"></span>
                Our Cuts
              </a>
            </li>
            <li>
              <a href="/contact" class="text-blue-200 hover:text-white hover:pl-2 transition-all duration-200 text-sm inline-flex items-center group">
                <span class="w-0 h-0.5 bg-blue-400 mr-0 group-hover:w-4 group-hover:mr-2 transition-all duration-200"></span>
                Contact
              </a>
            </li>
          </ul>
        </nav>

        <!-- Contact Info -->
        <div class="flex flex-col sm:col-span-2 lg:col-span-2">
          <h3 class="text-base sm:text-lg font-semibold mb-4 text-white flex items-center gap-2">
            <span class="w-1 h-6 bg-blue-400 rounded-full"></span>
            Get In Touch
          </h3>
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div class="space-y-3.5">
              <a href="tel:+62123456789" class="flex items-center gap-3 text-blue-200 hover:text-white transition-colors duration-200 text-sm group">
                <div class="bg-blue-800/50 p-2 rounded-lg group-hover:bg-blue-400 transition-colors">
                  <Phone class="w-4 h-4" />
                </div>
                <span>+62 123 456 789</span>
              </a>

              <a href="mailto:hello@neat.com" class="flex items-center gap-3 text-blue-200 hover:text-white transition-colors duration-200 text-sm group">
                <div class="bg-blue-800/50 p-2 rounded-lg group-hover:bg-blue-400 transition-colors">
                  <Mail class="w-4 h-4" />
                </div>
                <span>hello@neat.com</span>
              </a>
            </div>

            <div class="space-y-3.5">
              <div class="flex items-start gap-3 text-blue-200 text-sm">
                <div class="bg-blue-800/50 p-2 rounded-lg">
                  <MapPin class="w-4 h-4 shrink-0" />
                </div>
                <span>Jl. Style No. 42, Kota</span>
              </div>

              <div class="flex items-center gap-3 text-blue-200 text-sm">
                <div class="bg-blue-800/50 p-2 rounded-lg">
                  <Clock class="w-4 h-4" />
                </div>
                <span>20:00 – 22:00</span>
              </div>
            </div>
          </div>

          <!-- Social Media - Mobile Only -->
          <div class="flex sm:hidden gap-3 mt-6">
            <a
              href="https://facebook.com"
              target="_blank"
              rel="noopener"
              class="bg-blue-800/50 p-3 rounded-xl hover:bg-white hover:text-blue-900 transition-all duration-300 transform hover:scale-110"
              aria-label="Facebook"
            >
              <Facebook class="w-5 h-5" />
            </a>
            <a
              href="https://instagram.com"
              target="_blank"
              rel="noopener"
              class="bg-blue-800/50 p-3 rounded-xl hover:bg-white hover:text-blue-900 transition-all duration-300 transform hover:scale-110"
              aria-label="Instagram"
            >
              <Instagram class="w-5 h-5" />
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Copyright Bar -->
    <div class="border-t border-blue-800/50">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-5">
        <p class="text-center text-blue-300 text-xs sm:text-sm">
          © {{ new Date().getFullYear() }} Neat Hair Studio. All rights reserved.
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');

footer {
  font-family: 'Poppins', sans-serif;
}
</style>