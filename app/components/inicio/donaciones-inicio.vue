<template>
  <section class="relative py-24 bg-[#3E2781] overflow-hidden">
    <div class="absolute inset-0 z-0 opacity-20 pointer-events-none" 
         style="background-image: url('/images/pattern-clouds.png'); background-size: 800px;">
    </div>

    <div class="container mx-auto px-6 relative z-10">
      <div class="flex justify-center lg:pr-32">
        <h2 class="text-[#F2F2F2] text-4xl md:text-5xl font-black uppercase mb-4 tracking-tighter">
          Donaciones
        </h2>
      </div>

      <div class="relative flex flex-col lg:flex-row items-center lg:items-stretch">
        
        <div class="w-full lg:w-4/12 z-20 h-[400px] md:h-[550px] lg:-mr-16">
          <div class="group w-full h-full bg-gray-300 rounded-[2rem] shadow-2xl border-4 border-white/10 overflow-hidden relative">
            
            <div class="relative w-full h-full">
              <div 
                v-for="(img, index) in images" 
                :key="index"
                class="absolute inset-0 transition-opacity duration-1000 ease-in-out"
                :class="index === currentIndex ? 'opacity-100 z-10' : 'opacity-0 z-0'"
              >
                <NuxtImg 
                  :src="img" 
                  alt="Comunidad M&F" 
                  class="w-full h-full object-cover transform transition-transform duration-[5s]"
                  :class="index === currentIndex ? 'scale-110' : 'scale-100'"
                />
              </div>

              <div class="absolute inset-0 z-30 flex items-center justify-between px-4 opacity-0 group-hover:opacity-100 transition-opacity duration-300 pointer-events-none">
                <button 
                  @click="prevSlide" 
                  class="pointer-events-auto w-10 h-10 rounded-full bg-white/20 hover:bg-white/40 backdrop-blur-sm text-white flex items-center justify-center transition-all"
                >
                  <span class="text-2xl">❮</span>
                </button>
                <button 
                  @click="nextSlide" 
                  class="pointer-events-auto w-10 h-10 rounded-full bg-white/20 hover:bg-white/40 backdrop-blur-sm text-white flex items-center justify-center transition-all"
                >
                  <span class="text-2xl">❯</span>
                </button>
              </div>

              <div class="absolute bottom-6 left-0 w-full z-30 flex justify-center items-center gap-3">
                <button 
                  v-for="(_, index) in images" 
                  :key="index"
                  @click="goToSlide(index)"
                  class="h-2.5 rounded-full transition-all duration-300 shadow-sm"
                  :class="index === currentIndex ? 'bg-white w-8' : 'bg-white/50 w-2.5 hover:bg-white/80'"
                ></button>
              </div>
            </div>

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
              to="/"
              class="w-full max-w-[200px] bg-[#A61F2D] text-white font-black py-3 px-6 
                     rounded-t-none rounded-b-full text-center
                     hover:bg-[#8b1a26] transition-all uppercase italic tracking-widest text-sm shadow-md"
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
import { ref, onMounted, onUnmounted } from 'vue';

const images = [
  '/images/inicio/about-1.jpg',
  '/images/inicio/about-1.jpg',
  '/images/inicio/about-1.jpg'
];

const currentIndex = ref(0);
let timer = null;

const startTimer = () => {
  timer = setInterval(nextSlide, 5000);
};

const stopTimer = () => {
  if (timer) clearInterval(timer);
};

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % images.length;
};

const prevSlide = () => {
  currentIndex.value = (currentIndex.value - 1 + images.length) % images.length;
};

const goToSlide = (index) => {
  currentIndex.value = index;
  stopTimer();
  startTimer();
};

onMounted(startTimer);
onUnmounted(stopTimer);
</script>

<style scoped>
@media (min-width: 1024px) {
  .lg\:-mr-16 {
    margin-right: -4rem;
  }
  .bg-white {
    margin-top: 40px;
    margin-bottom: 40px;
  }
}

/* Efecto Ken Burns */
.scale-110 {
  transform: scale(1.1);
}

/* Ajuste para que las flechas no estorben en pantallas muy pequeñas */
@media (max-width: 640px) {
  .pointer-events-auto {
    width: 2.5rem;
    height: 2.5rem;
  }
}
</style>