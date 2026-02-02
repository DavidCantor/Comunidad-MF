<template>
  <section class="relative w-full h-screen overflow-hidden bg-[#1D0F26]">
    
    <transition-group 
      :name="direction === 'next' ? 'slide-next' : 'slide-prev'" 
      tag="div" 
      class="relative w-full h-full"
    >
      <div 
        v-for="(slide, index) in slides" 
        :key="slide.title"
        v-show="currentSlide === index"
        class="absolute inset-0 w-full h-full"
      >
        <div class="absolute inset-0 bg-linear-to-b from-[#1D0F26]/80 via-[#1D0F26]/40 to-[#1D0F26]/80 z-30 animate-fade-in"></div>
        
        <NuxtImg 
          :src="slide.image" 
          class="w-full h-full object-cover scale-animation animate-image-reveal"
          :loading="index === 0 ? 'eager' : 'lazy'"
        />

        <div class="absolute inset-0 z-40 flex items-center justify-center text-center">
          <div class="container mx-auto px-6">
            <div class="max-w-5xl mx-auto flex flex-col items-center">
              
              <span class="inline-block px-5 py-2 mb-6 text-[10px] sm:text-xs font-black tracking-[0.3em] text-white uppercase bg-[#A61F2D] rounded-full animate-slide-up-1">
                {{ slide.tag }}
              </span>
              
              <h1 class="text-4xl sm:text-7xl lg:text-8xl font-black text-[#F2F2F2] mb-6 leading-[0.9] italic uppercase tracking-tighter animate-slide-up-2">
                {{ slide.title }}
              </h1>
              
              <p class="text-lg sm:text-2xl text-gray-200 mb-10 leading-relaxed max-w-2xl font-light animate-slide-up-3">
                {{ slide.description }}
              </p>
              
              <div class="flex flex-col sm:flex-row items-center justify-center gap-4 w-full sm:w-auto animate-slide-up-4">
                <NuxtLink to="/proyectos" 
                  class="w-full sm:w-auto px-10 py-4 bg-[#A61F2D] text-white font-black rounded-t-none rounded-b-4xl hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-center shadow-xl">
                  Ver Proyectos
                </NuxtLink>
                <NuxtLink to="/nosotros" 
                  class="w-full sm:w-auto px-10 py-4 border-2 border-white text-white font-black rounded-t-none rounded-b-4xl hover:bg-white hover:text-[#1D0F26] transition-all uppercase italic tracking-widest backdrop-blur-sm text-center">
                  Nuestra Historia
                </NuxtLink>
              </div>

            </div>
          </div>
        </div>
      </div>
    </transition-group>

    <div class="absolute inset-0 z-50 hidden md:flex items-center justify-between px-6 pointer-events-none animate-fade-in-delayed">
      <button @click="prevSlide" class="pointer-events-auto p-4 rounded-full bg-white/5 text-white hover:bg-[#A61F2D] transition-all backdrop-blur-md border border-white/10 h-14 w-14 flex items-center justify-center">❮</button>
      <button @click="nextSlide" class="pointer-events-auto p-4 rounded-full bg-white/5 text-white hover:bg-[#A61F2D] transition-all backdrop-blur-md border border-white/10 h-14 w-14 flex items-center justify-center">❯</button>
    </div>

  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const currentSlide = ref(0)
const direction = ref('next')
let timer = null

const slides = [
  { tag: 'Evento Principal', title: 'CONCURSO 2SIDES 2024', description: 'El escenario donde el talento Hallyu cobra vida.', image: '/images/inicio/about-1.jpg' },
  { tag: 'Comunidad M&F', title: 'Cultura Asiática Mosquera', description: 'Espacios para la evolución personal y profesional.', image: '/images/inicio/about-1.jpg' },
  { tag: 'Trayectoria', title: 'Liderando desde 2019', description: 'Garantizando recreación e integración cultural.', image: '/images/inicio/about-1.jpg' }
]

const nextSlide = () => { direction.value = 'next'; currentSlide.value = (currentSlide.value + 1) % slides.length; resetTimer(); }
const prevSlide = () => { direction.value = 'prev'; currentSlide.value = (currentSlide.value - 1 + slides.length) % slides.length; resetTimer(); }
const goToSlide = (index) => { direction.value = index > currentSlide.value ? 'next' : 'prev'; currentSlide.value = index; resetTimer(); }
const resetTimer = () => { if (timer) clearInterval(timer); timer = setInterval(nextSlide, 7000); }

onMounted(() => { resetTimer() })
onUnmounted(() => { if (timer) clearInterval(timer) })
</script>

<style scoped>
/* --- ANIMACIONES DE ENTRADA AL CARGAR (PAGE LOAD) --- */

.animate-fade-in {
  animation: fadeIn 1.2s ease-out forwards;
}

.animate-image-reveal {
  animation: imageReveal 1.8s cubic-bezier(0.2, 1, 0.3, 1) forwards;
}

/* Escalonamiento de elementos (Slide Up) */
.animate-slide-up-1 { animation: slideUp 0.8s ease-out 0.3s both; }
.animate-slide-up-2 { animation: slideUp 0.8s ease-out 0.5s both; }
.animate-slide-up-3 { animation: slideUp 0.8s ease-out 0.7s both; }
.animate-slide-up-4 { animation: slideUp 0.8s ease-out 0.9s both; }
.animate-fade-in-delayed { animation: fadeIn 1s ease-out 1.2s both; }

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes imageReveal {
  from { opacity: 0; transform: scale(1.1); }
  to { opacity: 1; transform: scale(1); }
}

@keyframes slideUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

/* --- ESTILOS DEL CARRUSEL --- */
.slide-next-enter-active, .slide-next-leave-active, 
.slide-prev-enter-active, .slide-prev-leave-active { 
  transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1); 
}
.slide-next-enter-from { transform: translateX(100%); opacity: 0; }
.slide-next-leave-to { transform: translateX(-100%); opacity: 0; }
.slide-prev-enter-from { transform: translateX(-100%); opacity: 0; }
.slide-prev-leave-to { transform: translateX(100%); opacity: 0; }

.scale-animation { animation: slowZoom 20s infinite alternate linear; }
@keyframes slowZoom { from { transform: scale(1); } to { transform: scale(1.08); } }
</style>