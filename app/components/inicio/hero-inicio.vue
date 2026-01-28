<template>
  <section class="relative w-full h-screen overflow-hidden bg-[#271540] z-0">


    <transition-group name="slide-fade" tag="div" class="relative w-full h-full">
      <div 
        v-for="(slide, index) in slides" 
        :key="slide.title"
        v-show="currentSlide === index"
        class="absolute inset-0 w-full h-full"
      >
        <div class="absolute inset-0 bg-[#1D0F26]/50 z-30"></div>
        
        <NuxtImg 
          :src="slide.image" 
          :alt="slide.title"
          class="w-full h-full object-cover "
        />

        <div class="absolute inset-0 z-40 flex items-center justify-center text-center">
          <div class="container mx-auto px-4 sm:px-6">
            <div class="max-w-4xl mx-auto flex flex-col items-center">
              <span class="inline-block px-3 py-1 sm:px-5 sm:py-2 mb-4 sm:mb-8 text-[10px] sm:text-xs font-bold tracking-[0.2em] text-[#F2F2F2] uppercase bg-[#1D0F26]/60 backdrop-blur-md border border-white/10 rounded-full">
                {{ slide.tag }}
              </span>
              
              <h1 class="text-3xl sm:text-7xl lg:text-8xl font-black text-[#F2F2F2] mb-4 sm:mb-10 leading-[1.1] drop-shadow-2xl">
                {{ slide.title }}
              </h1>
              
              <p class="text-sm sm:text-xl lg:text-2xl text-gray-200 mb-8 sm:mb-12 leading-relaxed max-w-xs sm:max-w-2xl font-light">
                {{ slide.description }}
              </p>
              
              <div class="flex flex-col sm:flex-row items-center justify-center gap-4 sm:gap-6 w-full sm:w-auto">
                <button class="w-full sm:w-auto px-8 sm:px-12 py-3 sm:py-5 bg-[#F2F2F2] text-[#1D0F26] font-bold rounded-full hover:bg-white transition-all active:scale-95">
                  Ver Proyectos
                </button>
                <button class="w-full sm:w-auto px-8 sm:px-12 py-3 sm:py-5 border-2 border-[#F2F2F2] text-[#F2F2F2] font-bold rounded-full hover:bg-[#F2F2F2] hover:text-[#271540] transition-all active:scale-95">
                  Nuestra Historia
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </transition-group>

    <div class="absolute inset-0 z-50 hidden md:flex items-center justify-between px-6 pointer-events-none">
      <button @click="prevSlide" class="p-4 rounded-full bg-[#1D0F26]/30 text-[#F2F2F2] hover:bg-[#1D0F26] transition-all pointer-events-auto backdrop-blur-sm group">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-8 h-8 group-hover:-translate-x-1 transition-transform">
          <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
        </svg>
      </button>
      <button @click="nextSlide" class="p-4 rounded-full bg-[#1D0F26]/30 text-[#F2F2F2] hover:bg-[#1D0F26] transition-all pointer-events-auto backdrop-blur-sm group">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-8 h-8 group-hover:translate-x-1 transition-transform">
          <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
        </svg>
      </button>
    </div>

    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 z-50 flex gap-3 bg-[#1D0F26]/40 px-6 py-3 rounded-full backdrop-blur-md border border-white/5">
      <button 
        v-for="(_, index) in slides" 
        :key="index"
        @click="goToSlide(index)"
        :class="[
          'transition-all duration-500 rounded-full',
          currentSlide === index ? 'w-8 h-2 bg-[#F2F2F2]' : 'w-2 h-2 bg-[#F2F2F2]/30 hover:bg-[#F2F2F2]'
        ]"
      ></button>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
let timer = null

const slides = [
  {
    tag: 'Evento Principal',
    title: 'CONCURSO 2SIDES 2024',
    description: 'El escenario donde el talento Hallyu de la Sabana de Occidente cobra vida.',
    image: '/images/inicio/about-1.jpg'
  },
  {
    tag: 'Comunidad M&F',
    title: 'Cultura Asiática en Mosquera',
    description: 'Generando espacios de aprendizaje para la evolución personal y profesional.',
    image: '/images/inicio/about-1.jpg'
  },
  {
    tag: 'Trayectoria',
    title: 'Desde el 2019',
    description: 'Trabajando fuertemente para garantizar espacios de recreación e integración.',
    image: '/images/inicio/about-1.jpg'
  }
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % slides.length
}

const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + slides.length) % slides.length
}

const goToSlide = (index) => {
  currentSlide.value = index
}

onMounted(() => { timer = setInterval(nextSlide, 7000) })
onUnmounted(() => { clearInterval(timer) })
</script>

<style scoped>
/* Animación de entrada y salida */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
}

.slide-fade-enter-from {
  transform: translateX(100%);
  opacity: 0;
  filter: blur(10px);
}

.slide-fade-leave-to {
  transform: translateX(-100%);
  opacity: 0;
  filter: blur(10px);
}

/* Zoom suave constante en la imagen */
.scale-animation {
  animation: slowZoom 25s infinite alternate;
}

@keyframes slowZoom {
  from { transform: scale(1); }
  to { transform: scale(1.15); }
}
</style>