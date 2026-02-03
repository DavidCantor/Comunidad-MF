<template>
  <section class="relative py-12 md:py-24 lg:py-32 bg-[#3E2781] overflow-hidden reveal-section">
    
    <div class="container mx-auto px-6 relative z-10">
      <h2 class="text-[#F2F2F2] text-4xl md:text-6xl lg:text-7xl font-black uppercase mb-10 lg:mb-12 leading-tight drop-shadow-2xl reveal-title">
        ¿Quiénes Somos?
      </h2>

      <div class="relative bg-white lg:bg-white rounded-[2.5rem] lg:rounded-[3rem] shadow-2xl flex flex-col lg:flex-row items-stretch overflow-visible reveal-card">
        
        <div class="w-full lg:w-3/5 p-8 md:p-12 lg:p-16 xl:p-20 flex flex-col justify-center">
          <div class="space-y-4 xl:space-y-6 text-[#1D0F26] leading-relaxed text-base md:text-lg xl:text-xl reveal-content">
            <p>
              Somos una organización juvenil sin ánimo de lucro fundada el
              <span class="font-bold text-[#A61F2D]">16 de junio del 2019</span>, nuestro punto de operación principal
              se encuentra en la sabana de occidente.
            </p>
            <p>
              Nuestro objetivo es generar espacios de recreación y/o aprendizaje para la evolución personal y
              profesional de cada persona amante a las culturas asiáticas (Corea, Japón, Tailandia y China).
            </p>
            <p class="font-medium italic border-l-4 border-[#A61F2D] pl-4 bg-gray-50 py-3 text-sm md:text-base xl:text-lg">
              Actualmente somos parte activa de la PLATAFORMA DE JUVENTUDES DE MOSQUERA.
            </p>
          </div>

          <div class="mt-8 xl:mt-10 reveal-content" style="transition-delay: 200ms;">
            <NuxtLink to="/nosotros"
              class="inline-block w-full sm:w-auto text-center bg-[#A61F2D] text-white font-black px-8 xl:px-10 py-4 xl:py-5 rounded-tr-3xl rounded-bl-3xl hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest shadow-lg active:scale-95">
              SABER MÁS DE NOSOTROS
            </NuxtLink>
          </div>
        </div>

        <div class="w-full lg:w-2/5 p-6 lg:p-0 lg:relative reveal-grid">
          <div class="grid grid-cols-3 gap-3 md:gap-4 h-[250px] sm:h-[600px] lg:h-[110%] lg:absolute lg:inset-y-[-5%] lg:right-[-10%] lg:w-[120%] z-20">
            
            <div class="image-box w-full h-full overflow-hidden bg-gray-200 rounded-bl-[60px] md:rounded-bl-[120px] lg:rounded-bl-[140px] xl:rounded-bl-[180px] shadow-xl">
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Comunidad" class="w-full h-full object-cover" />
            </div>

            <div class="image-box w-full h-full overflow-hidden bg-gray-300 rounded-tl-[60px] md:rounded-tl-[120px] lg:rounded-tl-[140px] xl:rounded-tl-[180px] shadow-xl">
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Evento" class="w-full h-full object-cover" />
            </div>

            <div class="image-box w-full h-full overflow-hidden bg-gray-400 rounded-br-[60px] md:rounded-br-[120px] lg:rounded-br-[140px] xl:rounded-br-[180px] shadow-xl">
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Cultura" class="w-full h-full object-cover" />
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
/* Timeline base */
.reveal-section {
  view-timeline-name: --section;
  view-timeline-axis: block;
}

/* 1. Título: Aparece desde abajo */
.reveal-title {
  animation: revealUp both;
  animation-timeline: --section;
  animation-range: entry 10% cover 30%;
}

/* 2. Cuadro Blanco: Desliza desde la izquierda */
.reveal-card {
  animation: revealLeft both;
  animation-timeline: --section;
  animation-range: entry 15% cover 40%;
}

/* 3. Grid de Imágenes: Desliza desde la derecha y escala */
.reveal-grid {
  animation: revealRight both;
  animation-timeline: --section;
  animation-range: entry 20% cover 45%;
}

/* 4. Imágenes individuales (Efecto pop sutil) */
.image-box {
  animation: popScale both;
  animation-timeline: --section;
  animation-range: entry 25% cover 50%;
}

/* Keyframes */
@keyframes revealUp {
  from { opacity: 0; transform: translateY(60px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes revealLeft {
  from { opacity: 0; transform: translateX(-100px); }
  to { opacity: 1; transform: translateX(0); }
}

@keyframes revealRight {
  from { opacity: 0; transform: translateX(100px); }
  to { opacity: 1; transform: translateX(0); }
}

@keyframes popScale {
  from { opacity: 0; transform: scale(0.8); }
  to { opacity: 1; transform: scale(1); }
}

/* Hover effect original */
img {
  transition: transform 0.8s cubic-bezier(0.2, 1, 0.3, 1);
}

@media (hover: hover) {
  img:hover {
    transform: scale(1.1);
  }
}

/* Fallback para navegadores que no soportan animation-timeline */
@supports not (animation-timeline: --section) {
  .reveal-title, .reveal-card, .reveal-grid, .image-box {
    opacity: 1;
    transform: none;
  }
}
</style>