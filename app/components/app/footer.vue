<template>
  <footer class="bg-[#7f217d] text-white overflow-hidden relative">
    <!-- Fondo decorativo -->
    <div 
      class="absolute inset-0 opacity-[0.05] pointer-events-none scale-y-[-1] bg-repeat" 
      style="background-image: url('/images/Recurso-6.webp'); background-size: 1920px auto; z-index: 1;"
    ></div>

    <!-- Contenido principal -->
    <div class="container mx-auto px-4 sm:px-6 lg:px-8 pt-16 pb-12 relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 lg:gap-12">
        
        <!-- Logo y descripción -->
        <div class="flex flex-col items-center md:items-start space-y-4">
          <NuxtLink to="/" class="block group transition-transform hover:scale-[1.02]">
            <NuxtImg 
              src="/images/Recurso-4.webp" 
              alt="M&F Logo" 
              class="h-20 w-auto object-contain"
  
              loading="lazy"
            />
          </NuxtLink>
          <p class="text-white/75 text-center md:text-left text-sm leading-relaxed max-w-xs">
            Generando espacios de recreación y aprendizaje para la evolución personal y profesional 
            de los amantes de las culturas asiáticas.
          </p>
        </div>

        <!-- Navegación -->
        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-white text-lg lg:text-xl font-black uppercase italic mb-4 lg:mb-6 border-b-2 border-[#A61F2D] pb-1 w-full text-center md:text-left">
            Navegación
          </h3>
          <nav class="w-full">
            <ul class="space-y-2.5 lg:space-y-3">
              <li v-for="link in navigationLinks" :key="link.to">
                <NuxtLink 
                  :to="link.to" 
                  class="text-white/70 hover:text-white transition-colors duration-200 block text-center md:text-left hover:pl-1"
                  active-class="text-white font-medium"
                >
                  {{ link.text }}
                </NuxtLink>
              </li>
            </ul>
          </nav>
        </div>

        <!-- Contacto -->
        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-white text-lg lg:text-xl font-black uppercase italic mb-4 lg:mb-6 border-b-2 border-[#A61F2D] pb-1 w-full text-center md:text-left">
            Contacto
          </h3>
          <ul class="space-y-2.5 lg:space-y-3 w-full">
            <li v-for="(contact, index) in contactInfo" :key="index" class="group">
              <div v-if="contact.type === 'text'" class="flex items-center justify-center md:justify-start gap-2">
                <span class="text-lg flex-shrink-0">{{ contact.icon }}</span>
                <span class="text-white/70 group-hover:text-white transition-colors duration-200 text-center md:text-left">
                  {{ contact.text }}
                </span>
              </div>
              <a 
                v-else
                :href="contact.href"
                class="flex items-center justify-center md:justify-start gap-2 text-white/70 group-hover:text-white transition-colors duration-200"
              >
                <span class="text-lg flex-shrink-0">{{ contact.icon }}</span>
                <span class="text-center md:text-left">{{ contact.text }}</span>
              </a>
            </li>
          </ul>
        </div>

        <!-- Redes sociales y CTA -->
        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-white text-lg lg:text-xl font-black uppercase italic mb-4 lg:mb-6 border-b-2 border-[#A61F2D] pb-1 w-full text-center md:text-left">
            Síguenos
          </h3>
          
          <!-- Redes sociales -->
          <div class="flex gap-3 mb-6 lg:mb-8">
            <a 
              v-for="social in socialMedia" 
              :key="social.name"
              :href="social.url" 
              :aria-label="social.name"
              class="social-btn"
            >
              {{ social.initials }}
            </a>
          </div>
          
          <!-- Botón CTA -->
          <NuxtLink 
            to="/contacto"
            class="bg-[#A61F2D] text-white font-black py-3 px-8 rounded-t-none rounded-b-3xl text-sm uppercase italic tracking-wider hover:bg-[#8b1a26] transition-all duration-300 shadow-lg hover:shadow-xl active:scale-[0.98] w-full text-center block"
          >
            Escríbenos
          </NuxtLink>
        </div>
      </div>
    </div>

    <!-- Pie de página -->
    <div class="bg-[#1D0F26] relative z-20 py-6">
      <div class="container mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-center gap-4 text-white/40 text-xs md:text-sm uppercase tracking-[0.15em] font-medium">
          
          <!-- Copyright -->
          <p class="order-2 md:order-1">© 2026 M&F Organización Juvenil.</p>
          
          <!-- Enlaces legales -->
          <div class="order-1 md:order-2 flex gap-4 md:gap-6">
            <a 
              v-for="legalLink in legalLinks" 
              :key="legalLink.text"
              :href="legalLink.url" 
              class="hover:text-white transition-colors duration-200 text-white/60"
            >
              {{ legalLink.text }}
            </a>
          </div>
          
          <!-- Desarrollador -->
          <p class="order-3">
            Desarrollado por 
            <a 
              href="https://dacav.vercel.app/" 
              target="_blank" 
              rel="noopener noreferrer"
              class="text-[#A61F2D] hover:text-white transition-colors duration-200 font-black ml-1 border-b border-transparent hover:border-white"
            >
              DACAV
            </a>
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
// Datos de navegación
const navigationLinks = [
  { to: '/', text: 'Inicio' },
  { to: '/nosotros', text: '¿Quiénes Somos?' },
  { to: '/proyectos', text: 'Proyectos' },
  { to: '/actividades', text: 'Actividades' },
  { to: '/apoya', text: 'Donaciones' }
];

// Información de contacto
const contactInfo = [
  { type: 'text', icon: '📍', text: 'Mosquera, Cundinamarca' },
  { type: 'email', icon: '📧', text: 'comunidad.mxf@gmail.com', href: 'mailto:comunidad.mxf@gmail.com' },
  { type: 'phone', icon: '📱', text: '+57 302 703 5757', href: 'tel:+573027035757' }
];

// Redes sociales
const socialMedia = [
  { name: 'Instagram', initials: 'IG', url: '#' },
  { name: 'Facebook', initials: 'FB', url: '#' },
  { name: 'TikTok', initials: 'TK', url: '#' }
];

// Enlaces legales
const legalLinks = [
  { text: 'Privacidad', url: '#' },
  { text: 'Términos', url: '#' }
];
</script>

<style scoped>
/* Estilos CSS nativos para evitar problemas con Tailwind */
.social-btn {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 9999px;
  color: white;
  font-size: 14px;
  font-weight: bold;
  transition: all 300ms ease;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.social-btn:hover {
  background-color: white;
  color: #7f217d;
  transform: scale(1.1);
}

/* Mejoras en la transición de enlaces */
.nuxt-link-active {
  color: white;
  font-weight: 500;
}

/* Optimización para dispositivos móviles */
@media (max-width: 768px) {
  .container {
    padding-left: 1rem;
    padding-right: 1rem;
  }
  
  .grid > div {
    margin-bottom: 2rem;
  }
  
  .grid > div:last-child {
    margin-bottom: 0;
  }
}
</style>