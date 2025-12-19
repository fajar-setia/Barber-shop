<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { ChevronDown } from 'lucide-vue-next'
import gsap from 'gsap'

/* 1. siapkan ref ------------------------------------------ */
const target = ref(null)        // akan menunjuk <span>
let tl

/* 2. animasi setelah mount -------------------------------- */
onMounted(() => {
  /* 2a. kalimat asli */
  const text = target.value.textContent
  target.value.textContent = ''          // kosongkan

  /* 2b. pecah jadi <span> per huruf */
  ;[...text].forEach(ch => {
    const span = document.createElement('span')
    span.textContent = ch === ' ' ? '\u00A0' : ch
    span.style.opacity = 0
    target.value.appendChild(span)
  })

  /* 2c. timeline ketik → tunggu → hapus → ulang */
  tl = gsap.timeline({ repeat: -1, repeatDelay: 1.5 })
    .set(target.value.children, { opacity: 0 })
    .to(target.value.children, {
      opacity: 1,
      duration: 0.5,
      stagger: 0.07,
      ease: 'none'
    })
    .to({}, { duration: 1.2 })                 // jeda
    .to(target.value.children, {
      opacity: 0,
      duration: 0.03,
      stagger: 0.04,
      ease: 'none'
    })
})

/* 3. bersihkan saat unmount ------------------------------- */
onUnmounted(() => tl && tl.kill())
</script>

<template>
    <section class="relative z-10 min-h-screen flex items-center justify-center px-6 py-12">
      <div class="text-center max-w-4xl mx-auto">
        <h1 class="text-white text-5xl sm:text-6xl md:text-7xl font-bold mb-6 leading-tight animate-fade-in">
          Welcome to
          <span ref="target" class="text-transparent bg-clip-text bg-linear-to-r from-blue-400 to-blue-500">
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
</template>