<template>
  <nav class="sticky top-0 w-full z-100 bg-[#1D0F26] border-b border-white/5 transition-all duration-300 animate-header-down">
    <div 
      class="absolute inset-0 opacity-[0.15] pointer-events-none scale-y-[-1]" 
      style="background-image: url('/images/Recurso-3.webp'); background-size: cover; background-position: center; background-repeat: no-repeat; z-index: 1;">
    </div>

    <div class="container mx-auto flex items-center justify-between relative z-10 px-4 md:px-8 h-20 md:h-24">
      
      <NuxtLink to="/" class="group flex items-center transition-transform active:scale-95 animate-logo-delayed">
        <NuxtImg 
          src="/images/Recurso-4.webp" 
          alt="Logo Comunidad M&F" 
          class="h-12 md:h-16 w-auto object-contain group-hover:brightness-110 transition-all"
        />
      </NuxtLink>

      <ul class="hidden lg:flex items-center gap-x-8">
        <li 
          v-for="(item, index) in menuItems" 
          :key="item.path"
          :style="{ animationDelay: `${0.6 + (index * 0.1)}s` }"
          class="animate-slide-down-item"
        >
          <NuxtLink 
            :to="item.path" 
            class="nav-link text-sm font-black tracking-[0.2em] text-gray-400 hover:text-white uppercase italic"
          >
            {{ item.name }}
          </NuxtLink>
        </li>
      </ul>

      <button 
        @click="isOpen = !isOpen" 
        class="lg:hidden relative z-50 p-2 text-gray-300 hover:text-white animate-fade-in"
        aria-label="Menu"
      >
        <div class="w-6 h-5 flex flex-col justify-between">
          <span :class="['h-0.5 w-full bg-current transform transition-all duration-300', isOpen ? 'rotate-45 translate-y-2' : '']"></span>
          <span :class="['h-0.5 w-full bg-current transition-all duration-300', isOpen ? 'opacity-0' : '']"></span>
          <span :class="['h-0.5 w-full bg-current transform transition-all duration-300', isOpen ? '-rotate-45 -translate-y-2' : '']"></span>
        </div>
      </button>
    </div>
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

const nubesStyle = {
  backgroundImage: `url("data:image/svg+xml,%3Csvg width='100' height='60' viewBox='0 0 100 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 10c-5 0-9 4-9 9 0 1 0 2 .3 3.1C18.6 23.5 16 26.5 16 30c0 4.4 3.6 8 8 8h24c4.4 0 8-3.6 8-8 0-3.5-2.6-6.5-5.3-7.9.3-1.1.3-2.1.3-3.1 0-5-4-9-9-9-3.5 0-6.6 2-8 5-1.4-3-4.5-5-8-5z' fill='%23ffffff' fill-rule='evenodd'/%3E%3C/svg%3E")`,
  backgroundSize: '120px'
}
</script>

<style scoped>
/* --- ANIMACIONES DE ENTRADA DIRECTA --- */
@keyframes headerDown {
  from { transform: translateY(-100%); }
  to { transform: translateY(0); }
}

@keyframes slideDownItem {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

.animate-header-down { animation: headerDown 0.8s cubic-bezier(0.2, 1, 0.3, 1) forwards; }
.animate-fade-in { animation: fadeIn 1s ease-out forwards; }
.animate-slide-down-item { opacity: 0; animation: slideDownItem 0.6s ease-out forwards; }

/* --- LINKS Y ESTADOS ACTIVOS --- */
.nav-link {
  position: relative;
  transition: all 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 3px;
  bottom: -6px;
  left: 0;
  background-color: #A61F2D;
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: white;
}

.nav-link:hover::after,
.router-link-active.nav-link::after {
  width: 100%;
}

.router-link-active {
  color: white !important;
}

/* --- MENÚ MÓVIL --- */
.menu-slide-enter-active, .menu-slide-leave-active {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
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