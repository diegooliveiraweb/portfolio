
<template>
  <div id="sections" class="relative">
    <button @click="prevSlide" v-if="count"
      class="absolute btn-prev text-white top-5 xl:top-10 transition ease-in-out hover:scale-110 duration-300"
      :data-tooltip="pages[count - 1] ?? ''">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="w-8 h-8" viewBox="0 0 16 16">
        <path fill-rule="evenodd"
          d="M7.776 5.553a.5.5 0 0 1 .448 0l6 3a.5.5 0 1 1-.448.894L8 6.56 2.224 9.447a.5.5 0 1 1-.448-.894l6-3z" />
      </svg>
    </button>
    <swiper :modules="modules" :direction="'vertical'" :mousewheel="true" :navigation="true" :pagination="false" class="mySwiper"
      @swiper="onSwiper" @slideChange="onSlideChange">
      <swiper-slide>
        <Home />
      </swiper-slide>
      <swiper-slide>
        <Sobre />
      </swiper-slide>
      <swiper-slide>
        <Projetos />
      </swiper-slide>
      <swiper-slide>
        <Blog />
      </swiper-slide>
    </swiper>
    <button @click="nextSlide"
      class="absolute btn-next text-white bottom-5 xl:bottom-10 transition ease-in-out hover:scale-110 duration-300"
      :data-tooltip="pages[count + 1]" v-if="pages.length - 1 > count">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="w-8 h-8" viewBox="0 0 16 16">
        <path fill-rule="evenodd"
          d="M1.553 6.776a.5.5 0 0 1 .67-.223L8 9.44l5.776-2.888a.5.5 0 1 1 .448.894l-6 3a.5.5 0 0 1-.448 0l-6-3a.5.5 0 0 1-.223-.67z" />
      </svg>
    </button>
  </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Mousewheel, Pagination } from "swiper";
import "swiper/css";
import "swiper/css/pagination";
export default {
  name: 'IndexPage',
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperPages: null,
      count: 0,
      pages: ['Home', 'Sobre', 'Projetos', 'Blog']
    }
  },
  methods: {
    onSwiper(swiper) {
      this.swiperPages = swiper;
    },
    nextSlide() {
      this.swiperPages.slideNext();
      this.count++;
    },
    prevSlide() {
      this.swiperPages.slidePrev();
      this.count--;
    }, 
    onSlideChange(){
      this.count = this.swiperPages.activeIndex == 0 ? 0 : this.swiperPages.activeIndex + 1;
    }
  },
  setup() {
    useHead({
      title: 'Diego Oliveira - Desenvolvedor Web Full Stack',
      viewport: 'width=device-width, initial-scale=1, maximum-scale=1',
      charset: 'utf-8',
      meta: [
        { name: 'description', content: 'Olá! E sou o Diego. Um jovem entusiasta por desenvolvimento de software e um gamer, nas horas vagas. Minha carreira de programação começou a um ano e meio, desde então venho me aperfeiçoando cada vez mais.' },
        { name: 'theme-color', content: '#000000' },
      ],
    })
    return {
      modules: [Mousewheel, Pagination],
    };
  },
}
</script>
<style>
.bar {
  transform: translateY(-47px);
}

.swiper {
  width: 100%;
  height: 100vh;
}

.swiper-pagination-bullet {
  background-color: #ffffffe6 !important;
  opacity: 1;
}

.swiper-pagination-bullet-active {
  background-color: rgb(74, 222, 128) !important;
}

.swiper-button-next {
  position: absolute !important;
  top: 50% !important;
}
</style>
