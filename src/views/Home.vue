<script setup>
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";

import {
  ChevronDown,
  Scissors,
  Sparkles,
  Palette,
  Check,
  Star,
  User
} from 'lucide-vue-next'

import bgSection from '../assets/images/Section/bgSection.png'
import AboutNeat from '../assets/images/Section/aboutNeat.png'
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
    <section class="relative z-10 min-h-screen flex items-center justify-center px-6 py-12">
      <div class="text-center max-w-4xl mx-auto">
        <h1 class="text-white text-5xl sm:text-6xl md:text-7xl font-bold mb-6 leading-tight animate-fade-in">
          Welcome to
          <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-400 to-blue-500">
            Neat Hair Studio
          </span>
        </h1>
        <p class="text-white/90 text-xl sm:text-2xl md:text-3xl mb-8 font-light">
          Your Style, Our Passion
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <button class="px-8 py-4 bg-linear-to-r from-blue-500 to-blue-600 text-white font-semibold rounded-full hover:scale-105 transform transition-all duration-300 shadow-lg hover:shadow-blue-500/50">
            Book Appointment
          </button>
          <button class="px-8 py-4 bg-white/10 backdrop-blur-sm text-white font-semibold rounded-full border-2 border-white/30 hover:bg-white/20 transform transition-all duration-300">
            View Services
          </button>
        </div>
      </div>

      <!-- Scroll Indicator -->
      <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
        <ChevronDown class="w-6 h-6 text-white/70" />
      </div>
    </section>

    <!-- KONTEN UTAMA - Dimulai setelah Hero -->
    <main class="relative z-20 mt-screen">
      <!-- SERVICES SECTION -->
      <section id="services" class="py-20 px-6 bg-transparent">
        <div class="max-w-6xl mx-auto">
          <div class="text-center mb-16">
            <h2 class="text-4xl sm:text-5xl font-bold text-white mb-4">
              Our Premium Services
            </h2>
            <div class="w-24 h-1 bg-blue-500 mx-auto mb-6"></div>
            <p class="text-white text-lg max-w-2xl mx-auto">
              Experience luxury grooming with our expert stylists
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Service Card 1 -->
            <div class="group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20">
              <div class="w-16 h-16 bg-linear-to-br from-blue-400 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
                <Scissors class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">
                Haircut & Styling
              </h3>
              <p class="text-gray-400 mb-4">
                Professional cuts tailored to your unique style and personality
              </p>
              <p class="text-blue-500 font-bold text-xl">From $35</p>
            </div>

            <!-- Service Card 2 -->
            <div class="group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20">
              <div class="w-16 h-16 bg-linear-to-br from-blue-500 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
                <Sparkles class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">Beard Grooming</h3>
              <p class="text-gray-400 mb-4">
                Expert beard trimming, shaping, and maintenance services
              </p>
              <p class="text-blue-500 font-bold text-xl">From $25</p>
            </div>

            <!-- Service Card 3 -->
            <div class="group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20">
              <div class="w-16 h-16 bg-linear-to-br from-blue-500 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300">
                <Palette class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">Hair Coloring</h3>
              <p class="text-gray-400 mb-4">
                Premium coloring services with top-quality products
              </p>
              <p class="text-blue-500 font-bold text-xl">From $60</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ABOUT SECTION -->
      <section id="about" class="py-20 px-6 bg-transparent">
        <div class="max-w-6xl mx-auto">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div class="order-2 lg:order-1">
              <h2 class="text-4xl sm:text-5xl font-bold text-white mb-6">
                Why Choose
                <span class="text-transparent bg-clip-text bg-linear-to-r from-blue-400 to-blue-500 drop-shadow-xl drop-shadow-blue-500">
                  Neat Hair Studio?
                </span>
              </h2>
              <p class="text-gray-400 text-lg mb-8 leading-relaxed">
                With over 10 years of experience, our team of expert stylists is
                dedicated to bringing out the best in you. We combine
                traditional barbering techniques with modern trends to create
                looks that are uniquely yours.
              </p>

              <div class="space-y-4">
                <div class="flex items-start gap-4">
                  <div class="w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0">
                    <Check class="w-6 h-6 text-white" />
                  </div>
                  <div>
                    <h4 class="text-white font-semibold text-lg mb-1">
                      Expert Stylists
                    </h4>
                    <p class="text-gray-400">
                      Certified professionals with years of experience
                    </p>
                  </div>
                </div>

                <div class="flex items-start gap-4">
                  <div class="w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0">
                    <Check class="w-6 h-6 text-white" />
                  </div>
                  <div>
                    <h4 class="text-white font-semibold text-lg mb-1">
                      Premium Products
                    </h4>
                    <p class="text-gray-400">
                      Only the finest hair care products and tools
                    </p>
                  </div>
                </div>

                <div class="flex items-start gap-4">
                  <div class="w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0">
                    <Check class="w-6 h-6 text-white" />
                  </div>
                  <div>
                    <h4 class="text-white font-semibold text-lg mb-1">
                      Relaxing Atmosphere
                    </h4>
                    <p class="text-gray-400">
                      Comfortable environment for your grooming experience
                    </p>
                  </div>
                </div>
              </div>
            </div>

            <div class="order-1 lg:order-2">
              <div class="relative">
                <div class="absolute inset-0 bg-linear-to-r from-blue-500 to-blue-600 rounded-2xl transform rotate-3 drop-shadow-xl drop-shadow-blue-500"></div>
                <div class="relative bg-zinc-800 rounded-2xl p-8 transform -rotate-3 hover:rotate-0 transition-transform duration-600">
                  <img
                    :src="AboutNeat"
                    alt="Studio"
                    class="rounded-xl w-full h-96 object-cover"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- TESTIMONIALS SECTION -->
      <section class="py-20 px-6 bg-transparent">
        <div class="max-w-6xl mx-auto">
          <div class="text-center mb-16">
            <h2 class="text-4xl sm:text-5xl font-bold text-white mb-4">
              What Our Clients Say
            </h2>
            <div class="w-24 h-1 bg-linear-to-r from-blue-500 to-blue-600 mx-auto"></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Testimonial 1 -->
            <div class=" backdrop-blur-xl rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600">
              <div class="flex gap-1 mb-4">
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
              </div>
              <p class="text-white mb-6 italic">
                "Best haircut I've ever had! The attention to detail is
                incredible. Highly recommend!"
              </p>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center">
                  <User class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-white font-semibold">John Smith</p>
                  <p class="text-gray-400 text-sm">Regular Client</p>
                </div>
              </div>
            </div>

            <!-- Testimonial 2 -->
            <div class="backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600">
              <div class="flex gap-1 mb-4">
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
              </div>
              <p class="text-gray-300 mb-6 italic">
                "Professional service in a relaxing atmosphere. The team really
                knows their craft!"
              </p>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center">
                  <User class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-white font-semibold">Michael Chen</p>
                  <p class="text-gray-400 text-sm">Happy Customer</p>
                </div>
              </div>
            </div>

            <!-- Testimonial 3 -->
            <div class="backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600">
              <div class="flex gap-1 mb-4">
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
              </div>
              <p class="text-gray-300 mb-6 italic">
                "Amazing experience every time. They truly care about making you
                look your best!"
              </p>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center">
                  <User class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-white font-semibold">David Rodriguez</p>
                  <p class="text-gray-400 text-sm">Loyal Client</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- CTA SECTION -->
      <section id="contact" class="py-20 px-6 bg-transparent">
        <div class="max-w-4xl mx-auto text-center">
          <div class="backdrop-blur-sm bg-white/20 rounded-3xl p-12 shadow-2xl">
            <svg
              class="w-16 h-16 text-white mx-auto mb-6"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              viewBox="0 0 24 24"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
              />
            </svg>
            <h2 class="text-4xl sm:text-5xl font-bold text-white mb-4">
              Ready for a New Look?
            </h2>
            <p class="text-white/90 text-lg mb-8">
              Book your appointment today and experience the difference
            </p>
            <button class="px-10 py-4 bg-blue-500 text-white font-bold rounded-full hover:scale-105 transform transition-all duration-300 shadow-lg hover:shadow-blue-500/30">
              Schedule Now
            </button>
          </div>
        </div>
      </section>
    </main>

    <Footer />
  </div>
</template>

<style scoped>
.mt-screen {
  margin-top: 10vh;
}
</style>