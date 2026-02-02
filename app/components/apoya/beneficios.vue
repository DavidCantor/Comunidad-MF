<template>
  <section class="py-24 bg-[#F2F2F2]">
    <div class="container mx-auto px-6 text-center">
      <h2 class="text-[#271540] text-4xl font-black uppercase italic mb-16 tracking-tighter">
        ¿Por qué apoyarnos?
      </h2>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="item in beneficios" :key="item.id" 
          class="bg-white border-b-8 border-[#A61F2D] p-10 rounded-[2.5rem] shadow-lg hover:-translate-y-3 transition-transform">
          <div class="w-16 h-16 bg-[#271540] rounded-2xl flex items-center justify-center mx-auto mb-6">
             <NuxtImg src="/images/inicio/about-1.jpg" class="w-10 h-10 object-cover rounded-md opacity-50" />
          </div>
          <h4 class="text-[#1D0F26] font-black uppercase mb-4">{{ item.titulo }}</h4>
          <p class="text-gray-600 text-sm">{{ item.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const beneficios = [
  { id: 1, titulo: 'Impacto Social', desc: 'Tu apoyo financia talleres gratuitos para jóvenes de escasos recursos.' },
  { id: 2, titulo: 'Visibilidad', desc: 'Como aliado, tu marca estará presente en todos nuestros eventos masivos.' },
  { id: 3, titulo: 'Certificación', desc: 'Entregamos certificados de donación y voluntariado para tu perfil profesional.' }
]
</script>