<template>
  <section class="relative py-12 md:py-24 bg-[#3E2781] overflow-hidden">


    <div class="container mx-auto px-4 md:px-6 relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 md:gap-12">
        
        <div class="flex flex-col items-center">
          <h2 class="text-[#F2F2F2] text-3xl md:text-5xl font-black uppercase mb-6 md:mb-8 tracking-tighter text-center">
            Patrocinadores
          </h2>
          
          <div class="w-full bg-white rounded-[2rem] md:rounded-[3rem] p-6 md:p-12 shadow-2xl flex flex-col items-center justify-between min-h-[350px] md:min-h-[450px] relative">
            <div class="flex items-center justify-between w-full flex-1">
              <button class="text-gray-300 hover:text-gray-500 transition-colors p-2">
                <span class="text-2xl md:text-4xl">❮</span>
              </button>
              
              <div class="px-4 md:px-8 flex justify-center items-center">
                <NuxtImg 
                  src="/images/inicio/about-1.jpg" 
                  alt="Patrocinador Principal" 
                  class="max-w-full h-32 md:h-48 object-contain"
                />
              </div>

              <button class="text-gray-300 hover:text-gray-500 transition-colors p-2">
                <span class="text-2xl md:text-4xl">❯</span>
              </button>
            </div>

            <div class="mt-6 md:mt-8 w-full flex justify-center">
              <NuxtLink to="/contacto" 
                class="bg-[#A61F2D] text-white font-black px-6 md:px-10 py-3 rounded-t-none rounded-b-full hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-base md:text-lg shadow-lg text-center">
                Ser Patrocinador
              </NuxtLink>
            </div>
          </div>
        </div>

        <div class="flex flex-col items-center mt-8 lg:mt-0">
          <h2 class="text-[#F2F2F2] text-3xl md:text-5xl font-black uppercase mb-6 md:mb-8 tracking-tighter text-center">
            Aliados
          </h2>
          
          <div class="w-full bg-white rounded-[2rem] md:rounded-[3rem] p-6 md:p-12 shadow-2xl flex flex-col items-center justify-between min-h-[350px] md:min-h-[450px]">
            <div class="flex items-center justify-around w-full flex-1 gap-2 md:gap-4">
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Aliado 1" class="h-12 md:h-20 w-auto object-contain grayscale opacity-50" />
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Aliado Principal" class="h-24 md:h-40 w-auto object-contain" />
              <NuxtImg src="/images/inicio/about-1.jpg" alt="Aliado 3" class="h-12 md:h-20 w-auto object-contain grayscale opacity-50" />
            </div>

            <div class="mt-6 md:mt-8 w-full flex justify-center">
              <NuxtLink to="/contacto" 
                class="bg-[#A61F2D] text-white font-black px-6 md:px-10 py-3 rounded-t-none rounded-b-full hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-base md:text-lg shadow-lg text-center">
                Ser Aliado
              </NuxtLink>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.rounded-b-full {
  border-bottom-left-radius: 9999px;
  border-bottom-right-radius: 9999px;
}

.bg-white {
  transition: transform 0.3s ease;
}

@media (min-width: 768px) {
  .bg-white:hover {
    transform: translateY(-5px);
  }
}
</style>