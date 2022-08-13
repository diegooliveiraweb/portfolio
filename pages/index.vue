<template>
  <div class="flex h-screen w-full justify-center items-center bg-black overflow-x-hidden flex-col relative">
      <div class="p-8 max-w-screen-lg z-20">
          <h1 class="text-4xl xl:text-5xl text-white font-bold text-center mb-3">Diego Oliveira</h1>
          <h2 class="text-gray-100 text-2xl text-center bg-black p-1 inline-block">Portfólio</h2>
      </div>
      <div class="h-1 block bg-green-400 w-full bar z-10"></div>
      <span class="block h-10 w-10 bg-contain cristal absolute top-10 left-5"></span>
      <span class="block h-52 w-52 bg-contain cristal absolute top-36 left-2 cristal-big"></span>
      <span class="block h-10 w-10 bg-contain cristal absolute top-10 right-5"></span>
      <NuxtLink to="/blog" class="absolute btn-next text-white bottom-10 transition ease-in-out hover:scale-110 duration-300" data-tooltip="Next">
        <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="w-8 h-8" viewBox="0 0 16 16">
          <path fill-rule="evenodd" d="M1.553 6.776a.5.5 0 0 1 .67-.223L8 9.44l5.776-2.888a.5.5 0 1 1 .448.894l-6 3a.5.5 0 0 1-.448 0l-6-3a.5.5 0 0 1-.223-.67z"/>
        </svg>
      </NuxtLink>
  </div>
</template>
<script>
export default {
  name: 'IndexPage',
}
</script>
<style> 
  .bar{
  transform: translateY(-47px);
  }
</style>
