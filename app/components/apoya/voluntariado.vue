<template>
  <section class="relative py-24 bg-[#271540] overflow-hidden">
    <div class="container mx-auto px-6 relative z-10">
      <div class="flex flex-col lg:flex-row-reverse items-center gap-12">
        
        <div class="w-full lg:w-5/12 relative">
          <div class="absolute -inset-4 border-2 border-[#A61F2D] rounded-[3rem] rotate-3 z-0"></div>
          <NuxtImg 
            src="/images/inicio/about-1.jpg" 
            class="relative z-10 w-full h-[400px] object-cover rounded-[3rem] shadow-2xl"
          />
        </div>

        <div class="w-full lg:w-7/12 text-center lg:text-left">
          <h2 class="text-white text-4xl md:text-6xl font-black uppercase italic mb-6 leading-none">
            Sé parte del <span class="text-[#A61F2D]">Equipo</span>
          </h2>
          <p class="text-gray-300 text-lg mb-8 max-w-xl">
            ¿Tienes habilidades en danza, logística, diseño o idiomas? Buscamos jóvenes apasionados que quieran donar su tiempo y talento para hacer crecer la cultura asiática en la región.
          </p>
          <NuxtLink to="/registro-voluntario" 
            class="inline-block bg-white text-[#1D0F26] font-black px-10 py-4 rounded-t-none rounded-b-[2rem] hover:bg-[#A61F2D] hover:text-white transition-all uppercase italic tracking-widest shadow-xl">
            Quiero ser voluntario
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>