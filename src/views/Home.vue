<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import Navbar from "../components/Navbar.vue";
import Footer from "../components/Footer.vue";

const currentSlide = ref(0);
const slides = [
  {
    image: 'https://images.unsplash.com/photo-1585747860715-2ba37e788b70?w=1920&h=1080&fit=crop',
    title: 'Excellence in Every Cut',
    subtitle: 'Where Style Meets Precision'
  },
  {
    image: 'https://images.unsplash.com/photo-1503951914875-452162b0f3f1?w=1920&h=1080&fit=crop',
    title: 'Master Craftsmen',
    subtitle: 'Defining Modern Elegance'
  },
  {
    image: 'https://images.unsplash.com/photo-1621605815971-fbc98d665033?w=1920&h=1080&fit=crop',
    title: 'Premium Experience',
    subtitle: 'Elevate Your Style'
  }
];

let slideInterval;

onMounted(() => {
  slideInterval = setInterval(() => {
    currentSlide.value = (currentSlide.value + 1) % slides.length;
  }, 5000);
});

onUnmounted(() => {
  if (slideInterval) clearInterval(slideInterval);
});

const services = [
  { 
    icon: '✂️', 
    name: 'Signature Cut', 
    price: '$45', 
    desc: 'Personalized styling with expert precision',
    gradient: 'from-blue-500 to-cyan-400'
  },
  { 
    icon: '💈', 
    name: 'Royal Shave', 
    price: '$40', 
    desc: 'Hot towel luxury straight razor experience',
    gradient: 'from-cyan-500 to-blue-400'
  },
  { 
    icon: '🧔', 
    name: 'Beard Design', 
    price: '$35', 
    desc: 'Sculptured beard artistry and grooming',
    gradient: 'from-blue-600 to-cyan-500'
  },
  { 
    icon: '👑', 
    name: 'VIP Package', 
    price: '$85', 
    desc: 'Ultimate grooming luxury experience',
    gradient: 'from-cyan-600 to-blue-500'
  }
];

const barbers = [
  { name: 'Alex Rodriguez', role: 'Master Barber', exp: '12 Years', img: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=400&h=400&fit=crop' },
  { name: 'Marcus Chen', role: 'Style Director', exp: '15 Years', img: 'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?w=400&h=400&fit=crop' },
  { name: 'James Wilson', role: 'Senior Stylist', exp: '10 Years', img: 'https://images.unsplash.com/photo-1500648767791-00dcc994a43e?w=400&h=400&fit=crop' }
];

const testimonials = [
  { name: 'Michael R.', text: 'Absolutely phenomenal service! The atmosphere is incredible and the attention to detail is unmatched.', rating: 5 },
  { name: 'James K.', text: 'Best barbershop experience in the city. Professional, stylish, and always delivers perfection.', rating: 5 },
  { name: 'David L.', text: 'These artists transformed my look completely. Worth every visit!', rating: 5 }
];

const scrollProgress = ref(0);

const handleScroll = () => {
  const windowHeight = window.innerHeight;
  const documentHeight = document.documentElement.scrollHeight - windowHeight;
  scrollProgress.value = (window.scrollY / documentHeight) * 100;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="min-h-screen bg-white relative overflow-hidden">
    <!-- Progress Bar -->
    <div class="fixed top-0 left-0 w-full h-1 bg-blue-100 z-50">
      <div 
        class="h-full bg-gradient-to-r from-blue-500 to-cyan-400 transition-all duration-300"
        :style="{ width: scrollProgress + '%' }"
      ></div>
    </div>

    <!-- Floating Decorative Elements -->
    <div class="fixed top-20 left-10 w-72 h-72 bg-blue-200 rounded-full mix-blend-multiply filter blur-3xl opacity-30 animate-blob"></div>
    <div class="fixed top-40 right-10 w-72 h-72 bg-cyan-200 rounded-full mix-blend-multiply filter blur-3xl opacity-30 animate-blob animation-delay-2000"></div>
    <div class="fixed bottom-20 left-1/2 w-72 h-72 bg-blue-300 rounded-full mix-blend-multiply filter blur-3xl opacity-30 animate-blob animation-delay-4000"></div>
    
    <Navbar />
    
    <!-- Hero Slider -->
    <section class="relative h-screen overflow-hidden">
      <div 
        v-for="(slide, index) in slides" 
        :key="index"
        class="absolute inset-0 transition-all duration-1000"
        :class="currentSlide === index ? 'opacity-100 scale-100' : 'opacity-0 scale-110'"
      >
        <div class="absolute inset-0 bg-gradient-to-br from-blue-600/80 via-cyan-500/70 to-blue-400/80 z-10"></div>
        <img 
          :src="slide.image" 
          :alt="slide.title"
          class="w-full h-full object-cover"
        />
        <div class="absolute inset-0 z-20 flex items-center justify-center text-center px-4">
          <div class="max-w-5xl">
            <div class="inline-block mb-6 overflow-hidden">
              <h1 class="text-7xl md:text-9xl font-black text-white mb-4 tracking-tighter leading-none animate-slide-up">
                {{ slide.title }}
              </h1>
            </div>
            <p class="text-2xl md:text-4xl text-cyan-100 font-light mb-10 animate-slide-up animation-delay-200">
              {{ slide.subtitle }}
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center animate-slide-up animation-delay-400">
              <button class="group relative bg-white text-blue-600 font-bold px-12 py-5 rounded-full overflow-hidden transition-all duration-300 hover:scale-105 hover:shadow-2xl">
                <span class="relative z-10">BOOK APPOINTMENT</span>
                <div class="absolute inset-0 bg-gradient-to-r from-blue-500 to-cyan-400 transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left duration-300"></div>
                <span class="absolute inset-0 flex items-center justify-center text-white opacity-0 group-hover:opacity-100 transition-opacity duration-300 z-20">BOOK APPOINTMENT</span>
              </button>
              <button class="border-2 border-white text-white font-bold px-12 py-5 rounded-full hover:bg-white hover:text-blue-600 transition-all duration-300 hover:scale-105">
                LEARN MORE
              </button>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Slide Indicators -->
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 z-30 flex gap-3">
        <button 
          v-for="(_, index) in slides" 
          :key="index"
          @click="currentSlide = index"
          class="transition-all duration-300 rounded-full"
          :class="currentSlide === index ? 'w-16 h-2 bg-white' : 'w-2 h-2 bg-white/50 hover:bg-white/75'"
        ></button>
      </div>

      <!-- Scroll Indicator -->
      <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 z-30 animate-bounce">
        <div class="w-6 h-10 border-2 border-white/50 rounded-full p-1">
          <div class="w-1 h-2 bg-white rounded-full mx-auto animate-scroll"></div>
        </div>
      </div>
    </section>

    <!-- About Section with Parallax -->
    <section class="py-32 px-4 bg-gradient-to-br from-blue-50 via-white to-cyan-50 relative">
      <div class="max-w-7xl mx-auto">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
          <div class="relative">
            <div class="absolute -top-10 -left-10 w-64 h-64 bg-blue-200 rounded-full filter blur-3xl opacity-30"></div>
            <img 
              src="https://images.unsplash.com/photo-1585747860715-2ba37e788b70?w=800&h=1000&fit=crop" 
              alt="Barbershop Interior"
              class="rounded-3xl shadow-2xl relative z-10 transform hover:scale-105 transition-transform duration-500"
            />
            <div class="absolute -bottom-10 -right-10 w-48 h-48 bg-gradient-to-br from-blue-500 to-cyan-400 rounded-3xl shadow-xl flex items-center justify-center z-20">
              <div class="text-center text-white">
                <div class="text-5xl font-black">38+</div>
                <div class="text-sm font-semibold">Years</div>
              </div>
            </div>
          </div>
          
          <div>
            <div class="inline-block mb-4">
              <span class="text-blue-500 font-bold text-sm tracking-widest uppercase">About Us</span>
              <div class="w-24 h-1 bg-gradient-to-r from-blue-500 to-cyan-400 mt-2"></div>
            </div>
            <h2 class="text-6xl font-black text-gray-900 mb-6 leading-tight">
              Crafting Style<br/>
              <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-cyan-500">Since 1985</span>
            </h2>
            <p class="text-xl text-gray-600 leading-relaxed mb-8">
              We're not just a barbershop—we're a destination for gentlemen who demand excellence. 
              Our master barbers blend traditional craftsmanship with contemporary techniques to create 
              looks that turn heads and boost confidence.
            </p>
            <div class="grid grid-cols-3 gap-6">
              <div class="text-center p-4 bg-white rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                <div class="text-4xl font-black text-transparent bg-clip-text bg-gradient-to-br from-blue-600 to-cyan-500">15K+</div>
                <div class="text-gray-600 text-sm font-semibold mt-2">Happy Clients</div>
              </div>
              <div class="text-center p-4 bg-white rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                <div class="text-4xl font-black text-transparent bg-clip-text bg-gradient-to-br from-blue-600 to-cyan-500">8</div>
                <div class="text-gray-600 text-sm font-semibold mt-2">Master Barbers</div>
              </div>
              <div class="text-center p-4 bg-white rounded-2xl shadow-lg hover:shadow-xl transition-shadow">
                <div class="text-4xl font-black text-transparent bg-clip-text bg-gradient-to-br from-blue-600 to-cyan-500">5★</div>
                <div class="text-gray-600 text-sm font-semibold mt-2">Rating</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Services -->
    <section class="py-32 px-4 bg-white relative overflow-hidden">
      <div class="absolute top-0 right-0 w-96 h-96 bg-cyan-100 rounded-full filter blur-3xl opacity-30"></div>
      <div class="max-w-7xl mx-auto relative z-10">
        <div class="text-center mb-20">
          <span class="text-blue-500 font-bold text-sm tracking-widest uppercase">Our Services</span>
          <div class="w-24 h-1 bg-gradient-to-r from-blue-500 to-cyan-400 mx-auto mt-2 mb-6"></div>
          <h2 class="text-6xl font-black text-gray-900 mb-4">Premium Grooming</h2>
          <p class="text-2xl text-gray-600">Tailored experiences for the modern gentleman</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
          <div 
            v-for="service in services" 
            :key="service.name"
            class="group relative bg-white rounded-3xl p-8 shadow-xl hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-4 border border-gray-100 overflow-hidden"
          >
            <div :class="`absolute inset-0 bg-gradient-to-br ${service.gradient} opacity-0 group-hover:opacity-10 transition-opacity duration-500`"></div>
            <div class="relative z-10">
              <div class="text-7xl mb-6 transform group-hover:scale-110 transition-transform duration-300">{{ service.icon }}</div>
              <h3 class="text-3xl font-black text-gray-900 mb-3">{{ service.name }}</h3>
              <p class="text-gray-600 mb-6 leading-relaxed">{{ service.desc }}</p>
              <div class="flex items-center justify-between">
                <div :class="`text-4xl font-black text-transparent bg-clip-text bg-gradient-to-r ${service.gradient}`">{{ service.price }}</div>
                <button :class="`w-12 h-12 rounded-full bg-gradient-to-r ${service.gradient} flex items-center justify-center text-white transform group-hover:rotate-45 transition-transform duration-300 shadow-lg`">
                  →
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="py-32 px-4 bg-gradient-to-br from-blue-600 to-cyan-500 relative overflow-hidden">
      <div class="absolute inset-0 opacity-10">
        <div class="absolute top-10 left-10 w-64 h-64 border-4 border-white rounded-full"></div>
        <div class="absolute bottom-10 right-10 w-96 h-96 border-4 border-white rounded-full"></div>
      </div>
      <div class="max-w-7xl mx-auto relative z-10">
        <div class="text-center mb-20">
          <span class="text-cyan-100 font-bold text-sm tracking-widest uppercase">Meet The Team</span>
          <div class="w-24 h-1 bg-white mx-auto mt-2 mb-6"></div>
          <h2 class="text-6xl font-black text-white mb-4">Master Barbers</h2>
          <p class="text-2xl text-cyan-50">Artists behind your perfect look</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-10">
          <div 
            v-for="barber in barbers" 
            :key="barber.name"
            class="group relative"
          >
            <div class="relative overflow-hidden rounded-3xl shadow-2xl">
              <img 
                :src="barber.img" 
                :alt="barber.name"
                class="w-full h-96 object-cover transform group-hover:scale-110 transition-transform duration-700"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-blue-900 via-blue-900/50 to-transparent opacity-80"></div>
              <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
                <h3 class="text-3xl font-black mb-2">{{ barber.name }}</h3>
                <p class="text-cyan-200 text-lg mb-1">{{ barber.role }}</p>
                <p class="text-cyan-100 text-sm">{{ barber.exp }} Experience</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Gallery -->
    <section class="py-32 px-4 bg-gray-50">
      <div class="max-w-7xl mx-auto">
        <div class="text-center mb-20">
          <span class="text-blue-500 font-bold text-sm tracking-widest uppercase">Portfolio</span>
          <div class="w-24 h-1 bg-gradient-to-r from-blue-500 to-cyan-400 mx-auto mt-2 mb-6"></div>
          <h2 class="text-6xl font-black text-gray-900 mb-4">Our Masterpieces</h2>
          <p class="text-2xl text-gray-600">Every cut tells a story</p>
        </div>
        
        <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
          <div class="relative aspect-square overflow-hidden rounded-3xl group shadow-xl">
            <img 
              src="https://images.unsplash.com/photo-1622286342621-4bd786c2447c?w=600&h=600&fit=crop" 
              alt="Work 1"
              class="w-full h-full object-cover transform group-hover:scale-125 group-hover:rotate-3 transition-all duration-700"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-blue-600 to-transparent opacity-0 group-hover:opacity-90 transition-opacity duration-300 flex items-end justify-center pb-8">
              <span class="text-white font-bold text-xl">Classic Fade</span>
            </div>
          </div>
          <div class="relative aspect-square overflow-hidden rounded-3xl group shadow-xl">
            <img 
              src="https://images.unsplash.com/photo-1599351431202-1e0f0137899a?w=600&h=600&fit=crop" 
              alt="Work 2"
              class="w-full h-full object-cover transform group-hover:scale-125 group-hover:rotate-3 transition-all duration-700"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-cyan-600 to-transparent opacity-0 group-hover:opacity-90 transition-opacity duration-300 flex items-end justify-center pb-8">
              <span class="text-white font-bold text-xl">Modern Style</span>
            </div>
          </div>
          <div class="relative aspect-square overflow-hidden rounded-3xl group shadow-xl">
            <img 
              src="https://images.unsplash.com/photo-1621605815971-fbc98d665033?w=600&h=600&fit=crop" 
              alt="Work 3"
              class="w-full h-full object-cover transform group-hover:scale-125 group-hover:rotate-3 transition-all duration-700"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-blue-600 to-transparent opacity-0 group-hover:opacity-90 transition-opacity duration-300 flex items-end justify-center pb-8">
              <span class="text-white font-bold text-xl">Premium Cut</span>
            </div>
          </div>
          <div class="relative aspect-square overflow-hidden rounded-3xl group shadow-xl">
            <img 
              src="https://images.unsplash.com/photo-1633681926022-84c23e8cb2d6?w=600&h=600&fit=crop" 
              alt="Work 4"
              class="w-full h-full object-cover transform group-hover:scale-125 group-hover:rotate-3 transition-all duration-700"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-cyan-600 to-transparent opacity-0 group-hover:opacity-90 transition-opacity duration-300 flex items-end justify-center pb-8">
              <span class="text-white font-bold text-xl">Signature Look</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="py-32 px-4 bg-white relative overflow-hidden">
      <div class="absolute bottom-0 left-0 w-96 h-96 bg-blue-100 rounded-full filter blur-3xl opacity-30"></div>
      <div class="max-w-6xl mx-auto relative z-10">
        <div class="text-center mb-20">
          <span class="text-blue-500 font-bold text-sm tracking-widest uppercase">Testimonials</span>
          <div class="w-24 h-1 bg-gradient-to-r from-blue-500 to-cyan-400 mx-auto mt-2 mb-6"></div>
          <h2 class="text-6xl font-black text-gray-900 mb-4">What Clients Say</h2>
          <p class="text-2xl text-gray-600">Excellence recognized by those who matter</p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div 
            v-for="(testimonial, index) in testimonials" 
            :key="testimonial.name"
            class="group relative bg-gradient-to-br from-blue-50 to-cyan-50 rounded-3xl p-10 shadow-xl hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-2 border-l-4"
            :class="index % 2 === 0 ? 'border-blue-500' : 'border-cyan-500'"
          >
            <div class="absolute top-6 right-6 text-8xl text-blue-100 opacity-50 font-serif">"</div>
            <div class="flex mb-6">
              <span v-for="n in testimonial.rating" :key="n" class="text-3xl">
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-500 to-cyan-400">★</span>
              </span>
            </div>
            <p class="text-gray-700 text-lg mb-8 leading-relaxed relative z-10">{{ testimonial.text }}</p>
            <div class="flex items-center">
              <div class="w-14 h-14 rounded-full bg-gradient-to-br from-blue-500 to-cyan-400 flex items-center justify-center text-white font-bold text-xl mr-4">
                {{ testimonial.name[0] }}
              </div>
              <div>
                <p class="text-gray-900 font-black text-lg">{{ testimonial.name }}</p>
                <p class="text-gray-500 text-sm">Verified Client</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA -->
    <section class="py-32 px-4 bg-gradient-to-br from-blue-600 via-blue-500 to-cyan-400 relative overflow-hidden">
      <div class="absolute inset-0">
        <div class="absolute top-20 left-20 w-96 h-96 bg-white rounded-full opacity-10 animate-pulse"></div>
        <div class="absolute bottom-20 right-20 w-64 h-64 bg-cyan-300 rounded-full opacity-10 animate-pulse animation-delay-1000"></div>
      </div>
      <div class="max-w-5xl mx-auto text-center relative z-10">
        <h2 class="text-7xl font-black text-white mb-6 leading-tight">
          Ready to Look<br/>Your Absolute Best?
        </h2>
        <p class="text-3xl text-cyan-50 mb-12 font-light">Book your transformation today</p>
        <div class="flex flex-col sm:flex-row gap-6 justify-center">
          <button class="group relative bg-white text-blue-600 font-black px-16 py-6 rounded-full text-xl overflow-hidden shadow-2xl hover:shadow-3xl transition-all duration-300 hover:scale-105">
            <span class="relative z-10">BOOK NOW</span>
            <div class="absolute inset-0 bg-gradient-to-r from-cyan-400 to-blue-500 transform scale-x-0 group-hover:scale-x-100 transition-transform origin-left duration-300"></div>
            <span class="absolute inset-0 flex items-center justify-center text-white opacity-0 group-hover:opacity-100 transition-opacity duration-300 z-20 font-black">BOOK NOW</span>
          </button>
          <button class="border-3 border-white text-white font-black px-16 py-6 rounded-full text-xl hover:bg-white hover:text-blue-600 transition-all duration-300 hover:scale-105 shadow-2xl">
            CALL US
          </button>
        </div>
        <p class="text-cyan-100 mt-8 text-lg">📞 (555) 123-4567 | 📍 123 Style Street, Downtown</p>
      </div>
    </section>

    <Footer />
  </div>
</template>

<style scoped>
@keyframes blob {
  0%, 100% {
    transform: translate(0, 0) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
}

@keyframes slide-up {
  from {
    opacity: 0;
    transform: translateY(40px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes scroll {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(10px);
  }
  100% {
    transform: translateY(0);
  }
}

.animate-blob {
  animation: blob 7s infinite;
}

.animation-delay-2000 {
  animation-delay: 2s;
}

.animation-delay-4000 {
  animation-delay: 4s;
}

.animate-slide-up {
  animation: slide-up 0.8s ease-out forwards;
}

.animation-delay-200 {
  animation-delay: 0.2s;
  opacity: 0;
}

.animation-delay-400 {
  animation-delay: 0.4s;
  opacity: 0;
}

.animate-scroll {
  animation: scroll 2s ease-in-out infinite;
}

.animation-delay-1000 {
  animation-delay: 1s;
}
</style>