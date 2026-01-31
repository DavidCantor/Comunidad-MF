<template>
  <nav class="sticky top-0 w-full z-[100] bg-[#1D0F26] border-b border-white/5 transition-all duration-300">
    <div 
  class="absolute inset-0 opacity-[0.3] pointer-events-none scale-y-[-1]" 
  style="background-image: url('/images/Recurso-3.webp'); background-size: cover; background-position: center; background-repeat: no-repeat; z-index: 1;">
</div>

    <div class="container mx-auto flex items-center justify-between relative z-10 px-4 md:px-8 h-20 md:h-24">
      
<NuxtLink to="/" class="group flex items-center transition-transform active:scale-95">
  <NuxtImg 
    src="/images/Recurso-4.webp" 
    alt="Logo Comunidad M&F" 
    class="h-12 md:h-16 w-auto object-contain group-hover:brightness-110 transition-all"
  />
</NuxtLink>

      <ul class="hidden lg:flex items-center gap-x-8">
        <li v-for="item in menuItems.slice(0)" :key="item.path">
          <NuxtLink :to="item.path" class="nav-link text-lg font-bold tracking-widest text-gray-400 hover:text-white uppercase">
            {{ item.name }}
          </NuxtLink>
        </li>

      </ul>

      <button 
        @click="isOpen = !isOpen" 
        class="lg:hidden relative z-50 p-2 text-gray-300 hover:text-white"
        aria-label="Menu"
      >
        <div class="w-6 h-5 flex flex-col justify-between">
          <span :class="['h-0.5 w-full bg-current transform transition-all', isOpen ? 'rotate-45 translate-y-2' : '']"></span>
          <span :class="['h-0.5 w-full bg-current transition-all', isOpen ? 'opacity-0' : '']"></span>
          <span :class="['h-0.5 w-full bg-current transform transition-all', isOpen ? '-rotate-45 -translate-y-2' : '']"></span>
        </div>
      </button>
    </div>

    <Transition name="menu-slide">
      <div v-if="isOpen" class="fixed inset-0 z-40 lg:hidden overflow-hidden">
        <div class="absolute inset-0 bg-black/60 backdrop-blur-sm" @click="isOpen = false"></div>
        
        <div class="absolute right-0 top-0 h-full w-[80%] max-w-sm bg-[#1D0F26] p-10 shadow-2xl border-l border-white/10">
          <div class="absolute inset-0 z-0 opacity-[0.05]" :style="nubesStyle"></div>
          
          <ul class="relative z-10 flex flex-col gap-8 mt-16">
            <li v-for="item in menuItems" :key="item.path">
              <NuxtLink 
                :to="item.path" 
                @click="isOpen = false"
                class="text-2xl font-black text-gray-200 hover:text-indigo-400 uppercase tracking-tighter block"
              >
                {{ item.name }}
              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </Transition>
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

// Patrón SVG de nubes asiáticas (Kumo) en base64
const nubesStyle = {
  backgroundImage: `url("data:image/svg+xml,%3Csvg width='100' height='60' viewBox='0 0 100 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 10c-5 0-9 4-9 9 0 1 0 2 .3 3.1C18.6 23.5 16 26.5 16 30c0 4.4 3.6 8 8 8h24c4.4 0 8-3.6 8-8 0-3.5-2.6-6.5-5.3-7.9.3-1.1.3-2.1.3-3.1 0-5-4-9-9-9-3.5 0-6.6 2-8 5-1.4-3-4.5-5-8-5z' fill='%23ffffff' fill-rule='evenodd'/%3E%3C/svg%3E")`,
  backgroundSize: '120px'
}
</script>

<style scoped>
.nav-link {
  position: relative;
  transition: color 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 1px;
  bottom: -4px;
  left: 0;
  background-color: #818cf8;
  transition: width 0.3s ease;
}

.nav-link:hover::after,
.router-link-active.nav-link::after {
  width: 100%;
}

.router-link-active {
  color: white !important;
}

.cta-button {
  background-color: #4f46e5;
  color: white;
  padding: 0.5rem 1.25rem;
  border-radius: 0.375rem;
  font-weight: bold;
  font-size: 0.75rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  transition: all 0.3s ease;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

.cta-button:hover {
  background-color: #4338ca;
}

.cta-button:active {
  transform: scale(0.95);
}

/* Animación de entrada lateral para móvil */
.menu-slide-enter-active, .menu-slide-leave-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.menu-slide-enter-from, .menu-slide-leave-to {
  opacity: 0;
}

.menu-slide-enter-from div:last-child {
  transform: translateX(100%);
}

.menu-slide-leave-to div:last-child {
  transform: translateX(100%);
}
</style>