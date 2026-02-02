<template>
  <section class="py-24 bg-[#F2F2F2]">
    <div class="container mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-[#271540] text-4xl md:text-5xl font-black uppercase italic tracking-tighter">
          Nuestros Valores
        </h2>
        <div class="w-24 h-2 bg-[#A61F2D] mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
        <div v-for="valor in valores" :key="valor.titulo" class="group flex flex-col items-center p-8 bg-white rounded-[2rem] shadow-md hover:shadow-xl transition-all hover:-translate-y-2">
          <div class="w-20 h-20 bg-[#271540] rounded-2xl flex items-center justify-center mb-6 group-hover:bg-[#A61F2D] transition-colors duration-300">
            <img src="/images/inicio/about-1.jpg" class="w-12 h-12 object-cover rounded-lg grayscale invert" />
          </div>
          <h4 class="text-[#1D0F26] font-black uppercase text-center text-sm md:text-base tracking-widest">
            {{ valor.titulo }}
          </h4>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const valores = [
  { titulo: 'Identidad' },
  { titulo: 'Innovación' },
  { titulo: 'Liderazgo' },
  { titulo: 'Comunidad' }
]
</script>