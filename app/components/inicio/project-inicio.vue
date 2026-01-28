<template>
  <section class="relative py-4 bg-[#402B8C] overflow-hidden">


    <div class="container mx-auto px-6 relative z-10 text-center">
      <h2 class="text-[#F2F2F2] text-4xl md:text-5xl font-black uppercase mb-16 tracking-tight">
        Nuestros Proyectos
      </h2>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(project, index) in projects" 
          :key="index"
          class="bg-white rounded-[3rem] shadow-2xl flex flex-col items-center p-10 min-h-[500px] justify-between transition-transform hover:scale-[1.02]"
        >
          <div class="w-full flex flex-col items-center">
            <NuxtImg 
              src="/images/inicio/about-1.jpg" 
              class="w-48 h-48 object-contain mb-4"
              alt="M&F Logo"
            />
            <h3 class="text-[#1D0F26] text-2xl font-black uppercase leading-tight">
              {{ project.title }}
            </h3>
          </div>

          <div class="flex flex-wrap justify-center gap-4 my-8">
            <div 
              v-for="i in project.logoCount" 
              :key="i"
              class="w-16 h-12 flex items-center justify-center"
            >
              <NuxtImg 
                src="/images/inicio/about-1.jpg" 
                class="max-w-full max-h-full object-contain grayscale opacity-80" 
                alt="Evento"
              />
            </div>
          </div>

          <NuxtLink 
            :to="project.link"
            class="w-full max-w-[200px] bg-[#A61F2D] text-white font-black py-3 px-6 
                   rounded-t-none rounded-b-full 
                   hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-sm"
          >
            Ver más
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Dirección de Eventos',
    link: '/proyectos/eventos',
    logoCount: 3
  },
  {
    title: 'Dirección de Contenido',
    link: '/proyectos/contenido',
    logoCount: 6 // Supera los 3, abrirá segunda línea automáticamente
  },
  {
    title: 'Dirección de Impacto',
    link: '/proyectos/impacto',
    logoCount: 3
  }
]
</script>

<style scoped>
/* Estilización adicional para asegurar que el botón se vea exactamente como en la imagen */
.rounded-b-full {
  border-bottom-left-radius: 9999px;
  border-bottom-right-radius: 9999px;
}

/* Efecto suave para los logos de eventos */
img {
  pointer-events: none;
  user-select: none;
}
</style>