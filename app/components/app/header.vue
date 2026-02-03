<template>
  <nav class="sticky top-[-1px] w-full z-[100] bg-[#1D0F26] border-b border-white/10 shadow-xl pt-[1px]">
    
    <div 
      class="absolute inset-0 opacity-10 pointer-events-none scale-y-[-1] bg-center bg-cover" 
      style="background-image: url('/images/Recurso-3.webp');">
    </div>

    <div class="container mx-auto px-6 lg:px-12 relative z-10">
      <div class="flex items-center justify-between h-20 md:h-28">
        
        <NuxtLink to="/" class="flex-shrink-0 transition-transform active:scale-95">
          <NuxtImg 
            src="/images/Recurso-4.webp" 
            alt="Logo M&F" 
            class="h-14 md:h-20 w-auto object-contain"
          />
        </NuxtLink>

        <div class="hidden lg:flex items-center space-x-10">
          <NuxtLink 
            v-for="item in menuItems" 
            :key="item.path"
            :to="item.path" 
            class="nav-link text-[13px] font-black tracking-[0.2em] text-gray-400 hover:text-white uppercase italic transition-colors"
          >
            {{ item.name }}
          </NuxtLink>
        </div>

        <button 
          @click="isOpen = !isOpen" 
          class="lg:hidden relative z-[110] p-2 text-white focus:outline-none"
          aria-label="Menu"
        >
          <div class="w-7 h-5 relative flex flex-col justify-between items-end">
            <span :class="['h-0.5 bg-white transition-all duration-300', isOpen ? 'w-full rotate-45 translate-y-2.5' : 'w-full']"></span>
            <span :class="['h-0.5 bg-white transition-all duration-200', isOpen ? 'opacity-0' : 'w-2/3']"></span>
            <span :class="['h-0.5 bg-white transition-all duration-300', isOpen ? 'w-full -rotate-45 -translate-y-2.5' : 'w-full']"></span>
          </div>
        </button>
      </div>
    </div>

    <transition
      enter-active-class="transition duration-300 ease-out"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition duration-200 ease-in"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div v-if="isOpen" class="fixed inset-0 top-0 z-[105] bg-[#1D0F26] lg:hidden flex flex-col items-center justify-center">
        
        <div 
          class="absolute inset-0 opacity-10 pointer-events-none scale-y-[-1] bg-center bg-cover" 
          style="background-image: url('/images/Recurso-3.webp');">
        </div>

        <div class="relative z-10 flex flex-col space-y-8 text-center">
          <NuxtLink 
            v-for="item in menuItems" 
            :key="item.path"
            :to="item.path"
            @click="isOpen = false"
            class="text-4xl font-black text-white hover:text-[#A61F2D] uppercase italic tracking-tighter transition-all"
          >
            {{ item.name }}
          </NuxtLink>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isOpen = ref(false)
const menuItems = [
  { name: 'Inicio', path: '/' },
  { name: 'Nosotros', path: '/nosotros' },
  { name: 'Proyectos', path: '/proyectos' },
  { name: 'Actividad', path: '/actividades' },
  { name: 'Apoya', path: '/apoya' }
]
</script>

<style scoped>
.nav-link {
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -4px;
  left: 0;
  background-color: #A61F2D;
  transition: width 0.3s ease;
}

.nav-link:hover::after,
.router-link-active.nav-link::after {
  width: 100%;
}

.router-link-active {
  color: white !important;
}

.router-link-active.text-4xl {
  color: #A61F2D !important;
}
</style>