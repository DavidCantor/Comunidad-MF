<template>
  <section class="relative py-16 md:py-32 bg-[#402B8C] overflow-hidden">
    
    <div class="hidden lg:block absolute top-1/2 -translate-y-1/2 left-4 right-4 md:left-12 md:right-12 lg:left-20 lg:right-10 h-[450px] bg-white rounded-[3rem] z-0 shadow-2xl"></div>

    <div class="container mx-auto px-6 relative z-10">
      <h2 class="text-[#F2F2F2] text-3xl md:text-6xl font-black uppercase mb-8 md:mb-4 leading-tight drop-shadow-2xl">
        ¿Quiénes Soms?
      </h2>

      <div class="relative flex flex-col lg:flex-row items-center lg:min-h-[650px] gap-8 lg:gap-0">
        
        <div class="w-full lg:w-7/12 p-6 md:p-6 lg:pr-24 z-10 flex flex-col justify-center bg-white lg:bg-transparent rounded-[2.5rem] lg:rounded-none shadow-xl lg:shadow-none">
          <div class="space-y-4 md:space-y-6 text-[#1D0F26] leading-relaxed text-base md:text-lg max-w-2xl">
               <p>
              Somos una organización juvenil sin ánimo de lucro fundada el 
              <span class="font-bold text-indigo-700">16 de junio del 2019</span>, nuestro punto de operación principal se encuentra en la sabana de occidente.
            </p>
            <p>
              Somos una organización juvenil sin ánimo de lucro fundada el 
              <span class="font-bold text-indigo-700">16 de junio del 2019</span>, nuestro punto de operación principal se encuentra en la sabana de occidente.
            </p>
            <p>
              Nuestro objetivo es generar espacios de recreación y/o aprendizaje para la evolución personal y profesional de cada persona amante a las culturas asiáticas (Corea, Japón, Tailandia y China).
            </p>
            <p class="font-medium italic border-l-4 border-indigo-500 pl-4 bg-gray-50 py-2 text-sm md:text-base">
              Actualmente somos parte activa de la PLATAFORMA DE JUVENTUDES DE MOSQUERA.
            </p>
          </div>

          <div class="mt-8">
            <NuxtLink to="/nosotros" 
              class="inline-block w-full sm:w-auto text-center bg-[#A61F2D] text-white font-black px-10 py-4 rounded-tr-3xl rounded-bl-3xl hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest shadow-lg active:scale-95">
              SABER MÁS DE NOSOTROS
            </NuxtLink>
          </div>
        </div>

        <div class="w-full lg:w-5/12 grid grid-cols-3 gap-4 md:gap-4 z-20 h-[300px] sm:h-[450px] md:h-[650px]">
          
          <div class="w-full h-full overflow-hidden bg-gray-200 rounded-bl-[180px] md:rounded-bl-[180px] shadow-2xl border-2 md:border-6 border-[#271540]">
            <NuxtImg src="/images/inicio/about-1.jpg" alt="Comunidad" class="w-full h-full object-cover" />
          </div>

          <div class="w-full h-full overflow-hidden bg-gray-300 rounded-tl-[180px] md:rounded-tl-[180px] shadow-2xl border-2 md:border-6 border-[#271540]">
            <NuxtImg src="/images/inicio/about-1.jpg" alt="Evento" class="w-full h-full object-cover" />
          </div>

          <div class="w-full h-full overflow-hidden bg-gray-400 rounded-br-[180px] md:rounded-br-[180px] shadow-2xl border-2 md:border-6 border-[#271540]">
            <NuxtImg src="/images/inicio/about-1.jpg" alt="Cultura" class="w-full h-full object-cover" />
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
@media (min-width: 1024px) {
  .grid {
    min-width: 500px;
  }
}

img {
  transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

/* En desktop mantenemos el hover, en móvil lo desactivamos para evitar saltos táctiles */
@media (hover: hover) {
  img:hover {
    transform: scale(1.1);
  }
}
</style>