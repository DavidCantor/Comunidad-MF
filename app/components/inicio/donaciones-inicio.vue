<template>
  <section class="relative py-24 bg-[#402B8C] overflow-hidden">


    <div class="container mx-auto px-6 relative z-10">
      <div class="flex justify-center lg:pr-32">
        <h2 class="text-[#F2F2F2] text-4xl md:text-5xl font-black uppercase mb-4 tracking-tighter">
          Donaciones
        </h2>
      </div>

      <div class="relative flex flex-col lg:flex-row items-center lg:items-stretch">
        
        <div class="w-full lg:w-4/12 z-20 h-[400px] md:h-[550px] lg:-mr-16">
          <div class="w-full h-full overflow-hidden bg-gray-300 rounded-[2rem] shadow-2xl border-4 border-white/10">
            <NuxtImg 
              src="/images/inicio/about-1.jpg" 
              alt="Comunidad M&F" 
              class="w-full h-full object-cover"
            />
          </div>
        </div>

        <div class="w-full lg:w-9/12 bg-white rounded-3xl lg:rounded-l-none lg:rounded-r-[3rem] p-8 md:p-16 lg:pl-32 shadow-2xl z-10 flex flex-col justify-center mt-[-2rem] lg:mt-0">
          <div class="space-y-6 text-[#1D0F26] leading-relaxed text-lg max-w-3xl">
            <p>
              Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat. 
            </p>
            <p>
              Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie consequat, vel illum dolore eu feugiat nulla facilisis at vero eros et accumsan et iusto odio dignissim qui blandit praesent luptatum zzril delenit augue duis dolore te feugait nulla facilisi.
            </p>
          </div>

          <div class="mt-10 flex justify-center">
          <NuxtLink 
            :to="project.link"
            class="w-full max-w-[200px] bg-[#A61F2D] text-white font-black py-3 px-6 
                   rounded-t-none rounded-b-full text-center
                   hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-sm"
          >
            Ver más
          </NuxtLink>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const project = {
  link: '/'
}
</script>

<style scoped>
/* Ajuste para que la imagen sobresalga por arriba y por abajo de la tarjeta blanca */
@media (min-width: 1024px) {
  .lg\:-mr-16 {
    margin-right: -4rem;
  }
  
  /* Forzamos que la tarjeta blanca sea un poco más baja que la imagen para el efecto 'overlap' */
  .bg-white {
    margin-top: 40px;
    margin-bottom: 40px;
  }
}

img {
  transition: transform 0.5s ease;
}
img:hover {
  transform: scale(1.05);
}
</style>