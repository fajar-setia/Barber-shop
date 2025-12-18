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
    <main class="grow pt-28">
      <!-- HERO SECTION -->
      <section
        class="relative bg-cover bg-center h-88 sm:h-95 md:h-120 flex items-center justify-center overflow-hidden"
        style="background-image: url('../assets/images/hero-bg.jpg')"
      >
        <!-- Gradient Overlay -->
        <div
          class="absolute inset-0 bg-linear-to-b from-black/60 via-black/50 to-black/70"
        ></div>

        <!-- Hero Content -->
        <div
          class="relative z-10 px-6 py-12 text-center max-w-4xl mx-auto animate-fade-in"
        >
          <h1
            class="text-white text-5xl sm:text-6xl md:text-7xl font-bold mb-6 leading-tight"
          >
            Welcome to
            <span
              class="text-transparent bg-clip-text bg-linear-to-r from-amber-400 to-orange-500"
              >Neat Hair Studio</span
            >
          </h1>
          <p
            class="text-white/90 text-xl sm:text-2xl md:text-3xl mb-8 font-light"
          >
            Your Style, Our Passion
          </p>
          <div class="flex flex-col sm:flex-row gap-4 justify-center">
            <button
              class="px-8 py-4 bg-linear-to-r from-amber-500 to-orange-600 text-white font-semibold rounded-full hover:scale-105 transform transition-all duration-300 shadow-lg hover:shadow-amber-500/50"
            >
              Book Appointment
            </button>
            <button
              class="px-8 py-4 bg-white/10 backdrop-blur-sm text-white font-semibold rounded-full border-2 border-white/30 hover:bg-white/20 transform transition-all duration-300"
            >
              View Services
            </button>
          </div>
        </div>

        <!-- Scroll Indicator -->
        <div
          class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce"
        >
          <ChevronDown class="w-6 h-6 text-white/70" />
        </div>
      </section>

      <!-- SERVICES SECTION -->
      <section class="py-20 px-6 bg-linear-to-b from-black to-gray-900">
        <div class="max-w-6xl mx-auto">
          <div class="text-center mb-16">
            <h2 class="text-4xl sm:text-5xl font-bold text-white mb-4">
              Our Premium Services
            </h2>
            <div
              class="w-24 h-1 bg-linear-to-r from-amber-500 to-orange-600 mx-auto mb-6"
            ></div>
            <p class="text-gray-400 text-lg max-w-2xl mx-auto">
              Experience luxury grooming with our expert stylists
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <!-- Service Card 1 -->
            <div
              class="group bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-amber-500/20"
            >
              <div
                class="w-16 h-16 bg-linear-to-br from-amber-500 to-orange-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
              >
                <Scissors class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">
                Haircut & Styling
              </h3>
              <p class="text-gray-400 mb-4">
                Professional cuts tailored to your unique style and personality
              </p>
              <p class="text-amber-500 font-bold text-xl">From $35</p>
            </div>

            <!-- Service Card 2 -->
            <div
              class="group bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-amber-500/20"
            >
              <div
                class="w-16 h-16 bg-linear-to-br from-amber-500 to-orange-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
              >
                <Sparkles class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">Beard Grooming</h3>
              <p class="text-gray-400 mb-4">
                Expert beard trimming, shaping, and maintenance services
              </p>
              <p class="text-amber-500 font-bold text-xl">From $25</p>
            </div>

            <!-- Service Card 3 -->
            <div
              class="group bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-amber-500/20"
            >
              <div
                class="w-16 h-16 bg-linear-to-br from-amber-500 to-orange-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
              >
                <Palette class="w-8 h-8 text-white" />
              </div>
              <h3 class="text-2xl font-bold text-white mb-3">Hair Coloring</h3>
              <p class="text-gray-400 mb-4">
                Premium coloring services with top-quality products
              </p>
              <p class="text-amber-500 font-bold text-xl">From $60</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ABOUT SECTION -->
      <section class="py-20 px-6 bg-gray-900">
        <div class="max-w-6xl mx-auto">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
            <div class="order-2 lg:order-1">
              <h2 class="text-4xl sm:text-5xl font-bold text-white mb-6">
                Why Choose
                <span
                  class="text-transparent bg-clip-text bg-linear-to-r from-amber-400 to-orange-500"
                  >Neat Hair Studio?</span
                >
              </h2>
              <p class="text-gray-400 text-lg mb-8 leading-relaxed">
                With over 10 years of experience, our team of expert stylists is
                dedicated to bringing out the best in you. We combine
                traditional barbering techniques with modern trends to create
                looks that are uniquely yours.
              </p>

              <div class="space-y-4">
                <div class="flex items-start gap-4">
                  <div
                    class="w-12 h-12 bg-amber-500/20 rounded-lg flex items-center justify-center shrink-0"
                  >
                    <Check class="w-6 h-6 text-amber-500" />
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
                  <div
                    class="w-12 h-12 bg-amber-500/20 rounded-lg flex items-center justify-center shrink-0"
                  >
                    <Check class="w-6 h-6 text-amber-500" />
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
                  <div
                    class="w-12 h-12 bg-amber-500/20 rounded-lg flex items-center justify-center shrink-0"
                  >
                    <Check class="w-6 h-6 text-amber-500" />
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
                <div
                  class="absolute inset-0 bg-linear-to-r from-amber-500 to-orange-600 rounded-2xl transform rotate-3"
                ></div>
                <div
                  class="relative bg-gray-800 rounded-2xl p-8 transform -rotate-1 hover:rotate-0 transition-transform duration-300"
                >
                  <img
                    src="../assets/images/about-placeholder.jpg"
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
      <section class="py-20 px-6 bg-linear-to-b from-gray-900 to-black">
        <div class="max-w-6xl mx-auto">
          <div class="text-center mb-16">
            <h2 class="text-4xl sm:text-5xl font-bold text-white mb-4">
              What Our Clients Say
            </h2>
            <div
              class="w-24 h-1 bg-linear-to-r from-amber-500 to-orange-600 mx-auto"
            ></div>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Testimonial 1 -->
            <div
              class="bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300"
            >
              <div class="flex gap-1 mb-4">
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
                <Star class="w-5 h-5 text-amber-500 fill-amber-500" />
              </div>
              <p class="text-gray-300 mb-6 italic">
                "Best haircut I've ever had! The attention to detail is
                incredible. Highly recommend!"
              </p>
              <div class="flex items-center gap-3">
                <div
                  class="w-12 h-12 bg-linear-to-br from-amber-500 to-orange-600 rounded-full flex items-center justify-center"
                >
                  <User class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-white font-semibold">John Smith</p>
                  <p class="text-gray-400 text-sm">Regular Client</p>
                </div>
              </div>
            </div>

            <!-- Testimonial 2 -->
            <div
              class="bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300"
            >
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
                <div
                  class="w-12 h-12 bg-linear-to-br from-amber-500 to-orange-600 rounded-full flex items-center justify-center"
                >
                  <User class="w-6 h-6 text-white" />
                </div>
                <div>
                  <p class="text-white font-semibold">Michael Chen</p>
                  <p class="text-gray-400 text-sm">Happy Customer</p>
                </div>
              </div>
            </div>

            <!-- Testimonial 3 -->
            <div
              class="bg-gray-800/50 backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:border-amber-500/50 transition-all duration-300"
            >
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
                <div
                  class="w-12 h-12 bg-linear-to-br from-amber-500 to-orange-600 rounded-full flex items-center justify-center"
                >
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
      <section class="py-20 px-6 bg-black">
        <div class="max-w-4xl mx-auto text-center">
          <div
            class="bg-linear-to-r from-amber-500 to-orange-600 rounded-3xl p-12 shadow-2xl"
          >
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
            <button
              class="px-10 py-4 bg-white text-amber-600 font-bold rounded-full hover:scale-105 transform transition-all duration-300 shadow-lg hover:shadow-white/30"
            >
              Schedule Now
            </button>
          </div>
        </div>
      </section>
    </main>

    <Footer />
  </div>
</template>
