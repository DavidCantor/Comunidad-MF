<template>
  <footer class="bg-[#1D0F26] text-white pt-16 pb-8 overflow-hidden relative">


    <div class="container mx-auto px-6 relative z-10">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
        
        <div class="flex flex-col items-center md:items-start">
          <NuxtLink to="/" class="mb-6">
            <img 
              src="/images/inicio/about-1.jpg" 
              alt="M&F Logo" 
              class="h-20 w-20 object-cover rounded-xl shadow-lg border-2 border-[#A61F2D]"
            />
          </NuxtLink>
          <p class="text-gray-400 text-center md:text-left text-sm leading-relaxed">
            Generando espacios de recreación y aprendizaje para la evolución personal y profesional de los amantes de las culturas asiáticas.
          </p>
        </div>

        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-[#F2F2F2] text-xl font-black uppercase italic mb-6 border-b-2 border-[#A61F2D] pb-1">
            Navegación
          </h3>
          <ul class="space-y-3 text-center md:text-left">
            <li><NuxtLink to="/" class="text-gray-400 hover:text-white transition-colors">Inicio</NuxtLink></li>
            <li><NuxtLink to="/nosotros" class="text-gray-400 hover:text-white transition-colors">¿Quiénes Somos?</NuxtLink></li>
            <li><NuxtLink to="/proyectos" class="text-gray-400 hover:text-white transition-colors">Proyectos</NuxtLink></li>
            <li><NuxtLink to="/actividades" class="text-gray-400 hover:text-white transition-colors">Actividades</NuxtLink></li>
            <li><NuxtLink to="/apoya" class="text-gray-400 hover:text-white transition-colors">Donaciones</NuxtLink></li>
          </ul>
        </div>

        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-[#F2F2F2] text-xl font-black uppercase italic mb-6 border-b-2 border-[#A61F2D] pb-1">
            Contacto
          </h3>
          <ul class="space-y-3 text-center md:text-left text-gray-400">
            <li>📍 Mosquera, Cundinamarca</li>
            <li>📧 contacto@mfweb.com</li>
            <li>📱 +57 300 000 0000</li>
          </ul>
        </div>

        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-[#F2F2F2] text-xl font-black uppercase italic mb-6 border-b-2 border-[#A61F2D] pb-1">
            Síguenos
          </h3>
          <div class="flex gap-4 mb-6">
            <a href="#" class="w-10 h-10 bg-[#A61F2D] rounded-full flex items-center justify-center hover:scale-110 transition-transform shadow-md">
              <span class="text-xs font-bold">IG</span>
            </a>
            <a href="#" class="w-10 h-10 bg-[#A61F2D] rounded-full flex items-center justify-center hover:scale-110 transition-transform shadow-md">
              <span class="text-xs font-bold">FB</span>
            </a>
            <a href="#" class="w-10 h-10 bg-[#A61F2D] rounded-full flex items-center justify-center hover:scale-110 transition-transform shadow-md">
              <span class="text-xs font-bold">TK</span>
            </a>
          </div>
          <NuxtLink 
            to="/contacto"
            class="bg-[#A61F2D] text-white font-black py-2 px-8 rounded-t-none rounded-b-full text-sm uppercase italic tracking-widest hover:bg-[#8b1a26] transition-colors shadow-lg"
          >
            Escríbenos
          </NuxtLink>
        </div>
      </div>

      <div class="border-t border-white/10 pt-8 flex flex-col md:flex-row justify-between items-center gap-4 text-gray-500 text-[10px] md:text-xs uppercase tracking-[0.2em] font-medium text-center">
        <p>© 2026 M&F Organización Juvenil.</p>
        
        <p>
          Desarrollado por 
          <a 
            href="https://dacav.vercel.app/" 
            target="_blank" 
            rel="noopener noreferrer"
            class="text-[#A61F2D] hover:text-white transition-colors font-black border-b border-transparent hover:border-white"
          >
            DACAV
          </a>
        </p>

        <div class="flex gap-6">
          <a href="#" class="hover:text-white transition-colors">Privacidad</a>
          <a href="#" class="hover:text-white transition-colors">Términos</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.rounded-b-full {
  border-bottom-left-radius: 9999px;
  border-bottom-right-radius: 9999px;
}
</style>