<template>
    <div
        class="flex flex-col min-h-screen w-full justify-center items-center overflow-x-hidden overflow-y-auto relative z-10">

        <div class="p-8 max-w-screen-lg z-20">
            <h1 class="text-4xl xl:text-5xl text-white font-bold text-center mb-3">Projetos</h1>
        </div>
        <span class="block h-9 w-10 bg-contain cristal absolute top-16 left-5"></span>
        <span class="block h-14 w-14 bg-contain cristal absolute top-10 right-5"></span>
        <div class="container">
            <div class="hidden xl:block">
                <!-- <div class="p-5 xl:p-0 grid lg:grid-cols-2 xl:grid-cols-3 gap-4 2xl:gap-7 mb-6">
                    <div class="rounded-xl overflow-hidden relative project-post" v-for="p in projetos" :key="p.id">
                        <video autoplay="true" loop muted>
                            <source :src="p.src" type="video/mp4">
                        </video>
                        <div class="overlay absolute top-0 left-0 w-full h-full bg-[rgba(0,0,0,0.6)] flex items-center justify-center">
                            <div class="content p-4 xl:p-5">
                                <h4 class="text-xl text-white mb-3 font-bold" v-text="p.title"></h4>
                                <p class="text-xs lg:text-sm text-white" v-text="p.description"></p>
                                <div class="flex gap-2 mt-5">
                                    <a :href="p.url" target="_blank" rel="external" class="px-4 py-1 bg-green-600 bg-[url('~/assets/img/cristal.png')] bg-cover bg-center text-black font-medium rounded-xl transition ease-in-out hover:scale-105 duration-300">Visitar</a>
                                </div>
                            </div>
                        </div>
                    </div>
                
                </div> -->
                <swiper :slidesPerView="2" :spaceBetween="20" :pagination="{clickable: true}" :modules="modules"
                    class="swiper-projetos">
                    <swiper-slide v-for="p in projetos" :key="p.id" style="height: auto !important;">
                        <div class="rounded-xl overflow-hidden relative project-post">
                            <video autoplay="true" loop muted>
                                <source :src="p.src" type="video/mp4">
                            </video>
                            <div
                                class="overlay absolute top-0 left-0 w-full h-full bg-[rgba(0,0,0,0.6)] flex items-center justify-center">
                                <div class="content p-4 xl:p-5">
                                    <h4 class="text-xl text-white mb-3 font-bold" v-text="p.title"></h4>
                                    <p class="text-xs lg:text-sm text-white" v-text="p.description"></p>
                                    <div class="flex gap-2 mt-5">
                                        <a :href="p.url" target="_blank" rel="external"
                                            class="px-4 py-1 bg-green-600 bg-[url('~/assets/img/cristal.png')] bg-cover bg-center text-black font-medium rounded-xl transition ease-in-out hover:scale-105 duration-300">Visitar</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </swiper-slide>
                </swiper>
            </div>
            <div class="block xl:hidden px-5">
                <swiper :slidesPerView="'auto'" :spaceBetween="20" :pagination="true" :modules="modules"
                    class="swiper-projetos">
                    <swiper-slide v-for="p in projetos.slice(0, 3)" :key="p.id" style="height: auto !important;">
                        <div class="rounded-xl overflow-hidden relative project-post">
                            <video autoplay="true" loop muted>
                                <source :src="p.src" type="video/mp4">
                            </video>
                            <div
                                class="overlay absolute top-0 left-0 w-full h-full bg-[rgba(0,0,0,0.6)] flex items-center justify-center">
                                <div class="content p-4 xl:p-5">
                                    <h4 class="text-xl text-white mb-3 font-bold" v-text="p.title"></h4>
                                    <p class="text-xs lg:text-sm text-white" v-text="p.description"></p>
                                    <div class="flex gap-2 mt-5">
                                        <a :href="p.url" target="_blank" rel="external"
                                            class="px-4 py-1 bg-green-600 bg-[url('~/assets/img/cristal.png')] bg-cover bg-center text-black font-medium rounded-xl transition ease-in-out hover:scale-105 duration-300">Visitar</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </swiper-slide>
                </swiper>
                <swiper :slidesPerView="'auto'" :spaceBetween="20" :pagination="true" :modules="modules"
                    class="swiper-projetos">
                    <swiper-slide class="" v-for="p in projetos.slice(3)" :key="p.id" style="height: auto !important;">
                        <div class="rounded-xl overflow-hidden relative project-post">
                            <video autoplay="true" loop muted>
                                <source :src="p.src" type="video/mp4">
                            </video>
                            <div
                                class="overlay absolute top-0 left-0 w-full h-full bg-[rgba(0,0,0,0.6)] flex items-center justify-center">
                                <div class="content p-4 xl:p-5">
                                    <h4 class="text-xl text-white mb-3 font-bold" v-text="p.title"></h4>
                                    <p class="text-xs lg:text-sm text-white" v-text="p.description"></p>
                                    <div class="flex gap-2 mt-5">
                                        <a :href="p.url" target="_blank" rel="external"
                                            class="px-4 py-1 bg-green-600 bg-[url('~/assets/img/cristal.png')] bg-cover bg-center text-black font-medium rounded-xl transition ease-in-out hover:scale-105 duration-300">Visitar</a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </swiper-slide>
                </swiper>
            </div>
            <!-- <div class="text-center hidden xl:block">
                <button class="sm:w-auto px-4 py-2 bg-green-600 text-white mx-auto text-lg">Ver mais</button>
            </div> -->
        </div>
    </div>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";

// import required modules
import { Pagination } from "swiper";

export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    setup() {
        return {
            modules: [Pagination],
        };
    },
    name: 'BlogComponent',

    data() {
        return {
            projetos: [
                { id: 0, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/move-itaigara.mp4', title: 'Move Itaigara', description: 'Move Itaigara - Apartamentos de 3 quartos (suíte) com lavabo e 2 quartos (suíte) que faltava no Itaigara em Salvador.', url: 'https://moveitaigara.com.br/' },
                { id: 1, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/surfliving-ribeira.mp4', title: 'Surfliving - Surfing is a life changer.', description: 'Anyone who has ever stood on a surfboard, contemplated the ocean and it’s waves, observed surf lifestyle and the optics of the world through a surfers eyes knows.', url: '' },
                { id: 2, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/essenceestoril.mp4', title: 'Escolha o melhor de Estoril', description: 'Tudo o que importa. Escolha viver o melhor do Estoril.', url: '' },
                { id: 3, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/bloom-horto.mp4', title: 'Bloom Horto Florestal', description: 'O Bloom é um empreendimento que traz o inovador conceito Wellness em sua construção, que significa o perfeito equilíbrio entre todas as áreas da vida e a busca por um cotidiano mais saudável, próximo à natureza e em contato com a paz interior.', url: 'https://bloomhorto.com.br/' },
                { id: 4, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/maratona-programacao.mp4', title: 'Maratona de programação', description: 'Competição Maratona de Programação da Rede UniFTC estimula criatividade e inovação em alunos', url: 'https://www.uniftc.edu.br/noticias/competicao-maratona-de-programacao-da-rede-uniftc-estimula-criatividade-e-inovacao-em-alunos' },
                { id: 5, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/blue-barra.mp4', title: 'BLue Barra', description: 'Seja para morar ou para investir, o Blue Barra é uma excelente opção para sua vida...', url: 'http://www.bluebarra.com.br/' },
                { id: 6, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/horto-concept.mp4', title: 'Horto Concept', description: 'Projeto inovador e exclusivo, inspirado no design, bom gosto e arquitetura autoral.', url: 'https://hortoconcept.com.br/' },
                { id: 7, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/vivace-sim.mp4', title: 'Vivace SIM', description: 'O Vivace SIM dispõe de casas com 2/4 e uma infraestrutura completa de lazer para você viver os melhores momentos da vida, com a sua família.', url: 'http://estacao1construtora.com.br/vivace-sim/' },
                { id: 8, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/paradiso-papagaio.mp4', title: 'Paradiso Papagaio', description: ' E é pensando nos seus melhores momentos que o Paradiso Papagaio conta com uma infraestrutura completa de lazer.', url: 'http://estacao1construtora.com.br/vivace-papagaio/' },
                { id: 9, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/feirao-semana-tem-mais.mp4', title: 'Feirão: Semana Tem Mais', description: 'Casas e apartamentos, com preços imperdíveis, no endereço que você procura.', url: 'http://estacao1construtora.com.br/feirao-semana-tem-mais/' },
                { id: 10, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/genova.mp4', title: 'Génova', description: 'O Genova chegou para trazer uma nova chance para sua vida e para provar que morar bem é uma realidade possível para você.', url: 'http://estacao1construtora.com.br/genova/' },
                { id: 11, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/life-imbui.mp4', title: 'Life Imbuí', description: 'Seja para morar ou para investir, o Life Imbuí é uma excelente opção para sua vida, pois une uma localização estratégica à um projeto totalmente inovador com a qualidade construtiva de uma das construtoras mais tradicionais do mercado baiano.', url: 'https://lifeimbui.com.br/' },
                { id: 12, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/life-imbui-andamento-obra.mp4', title: 'Life Imbuí', description: 'Acompanhe o andamento da obra do Life imbui', url: 'http://estacao1construtora.com.br/genova/' },
                { id: 13, src: 'https://raw.githubusercontent.com/DiegoOliveiraDvJr/portfolio/main/assets/videos-projetos/colegio-thaiane.mp4', title: ' Colégio Thaiane Pinheiro', description: 'O Colégio Thaiane Pinheiro leva a cada um dos seus alunos uma formação humana e cidadã, pensando não só na sua formação profissional, mas acima de tudo, na construção de um ser humano pronto para enfrentar os desafios do mundo.', url: 'http://colegiothaianepinheiro.com.br/' },
           
           ]
        }
    },
}
</script>
<style>
.overlay {
    display: none;
}

.project-post:hover .overlay {
    display: flex;
}

.swiper-projetos .swiper-slide {
    width: 80%;
}
.swiper-projetos{
    height: auto !important;
}
.swiper-projetos .swiper-wrapper{
    padding: 50px 0;
}
@media(min-width:800px) {
    .swiper-projetos .swiper-slide {
        width: 100%;
    }
}
</style>