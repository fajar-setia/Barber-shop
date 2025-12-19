<script setup>
import { onMounted, nextTick } from "vue";
import {
  ChevronDown,
  Scissors,
  Sparkles,
  Palette,
  Check,
  Star,
  User,
} from "lucide-vue-next";

import AboutNeat from "../../assets/images/Section/aboutNeat.png";

onMounted(() => {
  nextTick(() => {
    // Load GSAP
    const script1 = document.createElement("script");
    script1.src =
      "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/gsap.min.js";
    document.head.appendChild(script1);

    script1.onload = () => {
      const script2 = document.createElement("script");
      script2.src =
        "https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.5/ScrollTrigger.min.js";
      document.head.appendChild(script2);

      script2.onload = () => {
        const gsap = window.gsap;
        const ScrollTrigger = window.ScrollTrigger;
        gsap.registerPlugin(ScrollTrigger);

        /* =========================================================
   1. SERVICES – Stagger Slide-Up + Overshoot Scale + Icon Spin
   =========================================================*/
        gsap.from('.service-card', {
  scrollTrigger: {
    trigger: '#services',   // pemicu scroll
    start: 'top 80%',       // saat #services 80% dari viewport
    toggleActions: 'play none none reverse'
  },
  opacity: 0,
  y: 80,
  scale: 0.7,
  duration: 1,
  ease: 'back.out(1.7)'
})

gsap.from('.service-icon', {
  scrollTrigger: {
    trigger: '#services',
    start: 'top 80%',
  },
  rotation: -360,
  scale: 0,
  duration: 1.2,
  ease: 'back.out(1.5)',
  delay: 0.3
})

        // === ABOUT SECTION - SPLIT REVEAL ===
        const aboutTl = gsap.timeline({
          scrollTrigger: {
            trigger: "#about",
            start: "top 70%",
            toggleActions: "play none none none",
          },
        });

        aboutTl
          .from(".about-title", {
            opacity: 0,
            x: -200,
            duration: 1,
            ease: "power4.out",
          })
          .from(
            ".about-highlight",
            {
              backgroundPosition: "-100% 0",
              duration: 1,
              ease: "power2.inOut",
            },
            "-=0.5"
          )
          .from(
            ".about-description",
            {
              opacity: 0,
              y: 50,
              duration: 0.8,
            },
            "-=0.5"
          );

        // Features - cascade effect
        gsap.from(".about-feature", {
          scrollTrigger: {
            trigger: ".about-features",
            start: "top 75%",
          },
          opacity: 0,
          x: -100,
          rotationY: -45,
          stagger: 0.15,
          duration: 0.8,
          ease: "back.out(1.7)",
        });

        // Feature icons - bounce
        gsap.from(".about-check-icon", {
          scrollTrigger: {
            trigger: ".about-features",
            start: "top 75%",
          },
          scale: 0,
          rotation: -180,
          stagger: 0.15,
          duration: 1,
          ease: "elastic.out(1, 0.6)",
        });

        // Image - 3D rotation entrance
        gsap.from(".about-img-container", {
          scrollTrigger: {
            trigger: "#about",
            start: "top 70%",
          },
          opacity: 0,
          x: 200,
          rotationY: 90,
          duration: 1.2,
          ease: "power3.out",
        });

        // Image continuous rotation
        gsap.to(".about-img-rotate", {
          rotation: 3,
          duration: 3,
          ease: "sine.inOut",
          yoyo: true,
          repeat: -1,
        });

        // === CTA SECTION - MEGA BOUNCE ===
        const ctaTl = gsap.timeline({
          scrollTrigger: {
            trigger: "#contact",
            start: "top 80%",
            toggleActions: "play none none none",
          },
        });

        ctaTl
          .from(".cta-container", {
            opacity: 0,
            scale: 0.3,
            y: 100,
            duration: 1.2,
            ease: "elastic.out(1, 0.5)",
          })
          .from(
            ".cta-icon-svg",
            {
              rotation: -720,
              scale: 0,
              duration: 1,
              ease: "back.out(2)",
            },
            "-=0.8"
          )
          .from(
            ".cta-title",
            {
              opacity: 0,
              y: 50,
              duration: 0.6,
            },
            "-=0.4"
          )
          .from(
            ".cta-text",
            {
              opacity: 0,
              y: 30,
              duration: 0.5,
            },
            "-=0.3"
          )
          .from(
            ".cta-btn",
            {
              opacity: 0,
              scale: 0,
              duration: 0.8,
              ease: "elastic.out(1, 0.6)",
            },
            "-=0.2"
          );

        // Button - Continuous pulse
        gsap.to(".cta-btn", {
          scale: 1.08,
          boxShadow: "0 0 40px rgba(59, 130, 246, 0.6)",
          duration: 1,
          yoyo: true,
          repeat: -1,
          ease: "sine.inOut",
        });

        // Icon rotation
        gsap.to(".cta-icon-svg", {
          rotation: 360,
          duration: 20,
          repeat: -1,
          ease: "none",
        });
      };
    };
  });
});
</script>

<template>
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
          <div
            class="service-card group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20"
          >
            <div
              class="service-icon w-16 h-16 bg-linear-to-br from-blue-400 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
            >
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
          <div
            class="service-card group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20"
          >
            <div
              class="service-icon w-16 h-16 bg-linear-to-br from-blue-500 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
            >
              <Sparkles class="w-8 h-8 text-white" />
            </div>
            <h3 class="text-2xl font-bold text-white mb-3">Beard Grooming</h3>
            <p class="text-gray-400 mb-4">
              Expert beard trimming, shaping, and maintenance services
            </p>
            <p class="text-blue-500 font-bold text-xl">From $25</p>
          </div>

          <!-- Service Card 3 -->
          <div
            class="service-card group backdrop-blur-lg rounded-2xl p-8 border border-gray-700/50 hover:border-blue-500/50 transition-all duration-300 hover:transform hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/20"
          >
            <div
              class="service-icon w-16 h-16 bg-linear-to-br from-blue-500 to-cyan-600 rounded-xl flex items-center justify-center mb-6 group-hover:rotate-6 transition-transform duration-300"
            >
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
            <h2
              class="about-title text-4xl sm:text-5xl font-bold text-white mb-6"
            >
              Why Choose
              <span
                class="about-highlight text-transparent bg-clip-text bg-linear-to-r from-blue-400 via-cyan-400 to-blue-500"
                style="background-size: 200% 100%"
              >
                Neat Hair Studio?
              </span>
            </h2>
            <p
              class="about-description text-gray-400 text-lg mb-8 leading-relaxed"
            >
              With over 10 years of experience, our team of expert stylists is
              dedicated to bringing out the best in you. We combine traditional
              barbering techniques with modern trends to create looks that are
              uniquely yours.
            </p>

            <div class="about-features space-y-4">
              <div class="about-feature flex items-start gap-4">
                <div
                  class="about-check-icon w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0"
                >
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

              <div class="about-feature flex items-start gap-4">
                <div
                  class="about-check-icon w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0"
                >
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

              <div class="about-feature flex items-start gap-4">
                <div
                  class="about-check-icon w-12 h-12 bg-blue-500 rounded-lg flex items-center justify-center shrink-0"
                >
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

          <div class="order-1 lg:order-2 about-img-container">
            <div class="relative">
              <div
                class="absolute inset-0 bg-linear-to-r from-blue-500 to-blue-600 rounded-2xl transform rotate-3"
              ></div>
              <div
                class="about-img-rotate relative bg-zinc-800 rounded-2xl p-8 transform -rotate-3 hover:rotate-0 transition-transform duration-600"
              >
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
          <div
            class="w-24 h-1 bg-linear-to-r from-blue-500 to-blue-600 mx-auto"
          ></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Testimonial 1 -->
          <div
            class="backdrop-blur-xl rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600"
          >
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
              <div
                class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center"
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
            class="backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600"
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
                class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center"
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
            class="backdrop-blur-sm rounded-2xl p-8 border border-gray-700/50 hover:shadow-2xl hover:shadow-blue-500/20 hover:scale-105 transition-all duration-600"
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
                class="w-12 h-12 bg-linear-to-br from-blue-500 to-blue-600 rounded-full flex items-center justify-center"
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
    <section id="contact" class="py-20 px-6 bg-transparent">
      <div class="max-w-4xl mx-auto text-center">
        <div
          class="cta-container backdrop-blur-sm bg-white/20 rounded-3xl p-12 shadow-2xl"
        >
          <svg
            class="cta-icon-svg w-16 h-16 text-white mx-auto mb-6"
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
          <h2 class="cta-title text-4xl sm:text-5xl font-bold text-white mb-4">
            Ready for a New Look?
          </h2>
          <p class="cta-text text-white/90 text-lg mb-8">
            Book your appointment today and experience the difference
          </p>
          <button
            class="cta-btn px-10 py-4 bg-blue-500 text-white font-bold rounded-full hover:scale-110 transform transition-all duration-300 shadow-lg"
          >
            Schedule Now
          </button>
        </div>
      </div>
    </section>
  </main>
</template>
